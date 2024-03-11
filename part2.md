## Step 1
open item.py file in our project
```bash
import scrapy



class BookscraperItem(scrapy.Item):
    # define the fields for your item here like:
    # name = scrapy.Field()
    pass
    
class BookItem(scrapy.Item):
    url = scrapy.Field()
    title = scrapy.Field()
    upc = scrapy.Field()
    product_type = scrapy.Field()
    price_excl_tax = scrapy.Field()
    price_incl_tax = scrapy.Field()
    tax = scrapy.Field()
    availability = scrapy.Field()
    number_of_reviews = scrapy.Field()
    star = scrapy.Field()
    category = scrapy.Field()
    description = scrapy.Field()
    price = scrapy.Field()
```
add all the file is not missing someone

## Step 2
import item.py in our bookspider

```bash
from bookscraper.items import BookItem, BookscraperItem
```
## step 3
make some changes in bookspider.py file

```bash
def parse_book_page(self, response):
        table_rows = response.css('.table tr')
        book_items = BookItem()
        
        book_items['url'] = response.url,
        book_items['title'] = response.css('.product_main h1::text').get(),
        book_items['upc'] = table_rows[0].css('td::text').get(),
        book_items['product_type'] = table_rows[1].css('td::text').get(),
        book_items['price_excl_tax'] = table_rows[2].css('td::text').get(),
        book_items['price_incl_tax'] = table_rows[3].css('td::text').get(),
        book_items['tax'] = table_rows[4].css('td::text').get(),
        book_items['availability'] = table_rows[5].css('td::text').get(),
        book_items['number_of_reviews'] = table_rows[6].css('td::text').get(),
        book_items['star'] = response.css('p.star-rating').attrib['class'],
        book_items['category'] = response.css('.breadcrumb li:nth-last-child(2) a::text').get(),
        book_items['description'] = response.css('div.product_description + p::text').get(),
        book_items['price'] = response.css('p.price_color::text').get()
            # 'review': review_items
        yield BookItem
```
## Step 4
now you see your test.json price SMBOLE `£` MAKE A SERLIZER for it
add this code in item.py file
```bash
 def serilize_price(value):
    return f'£{str(value)}'
```
now serlize it
```bash
class BookItem(scrapy.Item):
    url = scrapy.Field()
    title = scrapy.Field()
    upc = scrapy.Field()
    product_type = scrapy.Field()
    price_excl_tax = scrapy.Field(serilizer = serilize_price)
    price_incl_tax = scrapy.Field(serilizer = serilize_price)
    tax = scrapy.Field()
    availability = scrapy.Field()
    number_of_reviews = scrapy.Field()
    star = scrapy.Field()
    category = scrapy.Field()
    description = scrapy.Field()
    price = scrapy.Field(serilizer = serilize_price)
```
## Step 5
now look at pipelines.py
it use for clean a data

```bash
# useful for handling different item types with a single interface
from itemadapter import ItemAdapter


class BookscraperPipeline:
    def process_item(self, item, spider):
        return item
```
this class is empty because we don't need to do anything here yet. We will fill it out later on when we start dealing with any errors
you can add some method to clean the date
## Step 6
#### Strip all the whitespaces from strings
```bash
# Strip all the whitespaces from strings
        field_names = adapter.field_names()
        for field_name in field_names:
            if field_name != 'description':
                value = adapter.get(field_name)
                adapter[field_name] = value[0].strip()
```
## Step 7
#### category & product_type ---> switch to lowercase
```bash
for field_name in ['category', 'product_type']:
            if field_name in adapter:
                adapter[field_name] = adapter[field_name].lower()
```
## Step 8
#### price ---> convert to float and remove any non-numeric characters
```bash
price = adapter.get('price')
        if price:
            try:
                # Convert price to float and remove the pound symbol
                adapter['price'] = float(price.replace('£', ''))
            except ValueError:
                # Handle case where price cannot be converted to float
                adapter['price'] = None  # Or set to a default value
```
## Step 9
#### availability -- > extract number of bookings available
```bash
availability_string = adapter.get('availability')
        split_string_array = availability_string.split('(')
        if  len(split_string_array)<2 :
            adapter['availability'] = 0 
        else:
            availability_array =  split_string_array[1].strip(' ')
            adapter['availability'] = int(availability_array[0])  
      
```
## step 10
#### reviews ---> convert string to number

```bash
reviews = adapter.get('number_of_reviews')
adapter['number_of_reviews'] = int(reviews) if reviews else None
```
## Step 11
#### Convert star_rating to integer out of 5 stars
```bash
star_string = adapter.get('star_rating')
        if star_string:
            split_star_array = star_string.split('/')
            if len(split_star_array) > 1:
                star_text_value = split_star_array[0].strip().lower()
                if star_text_value == 'zero':
                    adapter['star'] = 0
                elif star_text_value == 'one':
                    adapter['star'] = 1
                elif star_text_value == 'two':
                    adapter['star'] = 2
                elif star_text_value == 'three':
                    adapter['star'] = 3
                elif star_text_value == 'four':
                    adapter['star'] = 4
                elif star_text_value == 'five':
                    adapter['star'] = 5
            else:
                adapter['star'] = None
        else:
            adapter['star'] = None
```
## Step 12
open setting.py file in text editor and uncomment

```bash
# Configure item pipelines
# See https://docs.scrapy.org/en/latest/topics/item-pipeline.html
ITEM_PIPELINES = {
   "bookscraper.pipelines.BookscraperPipeline": 300,
}

```
## Step 13
open a terminal  and run the following command in your project directory


```bash
scrapy crawl bookspider -o test2.json
```
This will save all the scraped data into `test2.json` file
You can open this json file using any text editor or you can use below python code snippet to view it on console
