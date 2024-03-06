# Scrapy-Tutoria
## Step 1
Making the virtual environment:
```bash
python -m venv venv
```
## Step 2
Activating the virtual environment:

```bash
venv\Scripts\activate
```
## Step 3
Installing packages using pip (Python package installer):

```bash
pip install scrapy
```
## Step 4

Checking if Scrapy was installed correctly:
```bash
scrapy version
```
This should display information about your installed Scrapy
version, including the Python and Twisted versions.
## Step 5
Now you can start building your first Scrapy spider by running the following command in the terminal:

```bash
 scrapy startproject bookscraper
```
The `startproject` command creates a new Scrapy project with the specified name. The generated project includes several directories that serve as containers for different
## Step 6
Navigate to the project folder:

```bash
cd  bookscraper
```
You will see a new structure inside this folder with  several files. The most important ones are `settings.py` and `items.py`. 
You will see a new structure inside this folder with several files. The most important ones are `items.py` which contains classes for storing data extracted 
## Step 7

```bash
 cd bookscraper
```
```bash
cd spiders
```
## Step 8
Create a new Spider by running one of the following commands:

For a basic Spider that extracts all links from a website:


```bash
scrapy genspider bookspider books.toscrape.com
```
Or for a Spider that follows links from page to page (also called CrawlSpider):
## Step 9
IPython provides a rich toolkit to help you make the most out of using Python interactively.  To install IPython run:
```bash
pip install ipython 
```
Then open `ipython` in your terminal with this command:

## Step 10
 Open `settings.py` file in an editor (e.g., At vscode or Sublime Text) 

 Open `scrapy.cfg` file in an editor (e.g., vim or nano) and add the following line inside it:
```bash
shell = ipython
```
```bash
[settings]
default = bookscraper.settings
shell = ipython

[deploy]
#url = http://localhost:6800/
project = bookscraper
```
Now, you can run Scrapy from within IPython using the `%run` magic function. To do so, just type:
```bash
scrapy shell
```
output :
```bash
 scrapy shell
2024-03-04 15:12:16 [scrapy.utils.log] INFO: Scrapy 2.11.1 started (bot: bookscraper)
2024-03-04 15:12:17 [scrapy.utils.log] INFO: Versions: lxml 5.1.0.0, libxml2 2.10.3, cssselect 1.2.0, parsel 1.8.1, w3lib 2.1.2, Twisted 24.3.0, Python 3.12.1 (tags/v3.12.1:2305ca5, Dec  7 2023, 22:03:25) [MSC v.1937 64 bit (AMD64)], pyOpenSSL 24.0.0 (OpenSSL 3.2.1 30 Jan 2024), cryptography 42.0.5, Platform Windows-10-10.0.19045-SP0
2024-03-04 15:12:17 [scrapy.addons] INFO: Enabled addons:
[]
2024-03-04 15:12:17 [asyncio] DEBUG: Using selector: SelectSelector
2024-03-04 15:12:17 [scrapy.utils.log] DEBUG: Using reactor: twisted.internet.asyncioreactor.AsyncioSelectorReactor
2024-03-04 15:12:17 [scrapy.utils.log] DEBUG: Using asyncio event loop: asyncio.windows_events._WindowsSelectorEventLoop
2024-03-04 15:12:17 [scrapy.extensions.telnet] INFO: Telnet Password: eb83c96f1901fd46
2024-03-04 15:12:17 [scrapy.middleware] INFO: Enabled extensions:
['scrapy.extensions.corestats.CoreStats',
 'scrapy.extensions.telnet.TelnetConsole']
2024-03-04 15:12:17 [scrapy.crawler] INFO: Overridden settings:
{'BOT_NAME': 'bookscraper',
 'DUPEFILTER_CLASS': 'scrapy.dupefilters.BaseDupeFilter',
 'FEED_EXPORT_ENCODING': 'utf-8',
 'LOGSTATS_INTERVAL': 0,
 'NEWSPIDER_MODULE': 'bookscraper.spiders',
 'REQUEST_FINGERPRINTER_IMPLEMENTATION': '2.7',
 'ROBOTSTXT_OBEY': True,
 'SPIDER_MODULES': ['bookscraper.spiders'],
 'TWISTED_REACTOR': 'twisted.internet.asyncioreactor.AsyncioSelectorReactor'}
2024-03-04 15:12:17 [scrapy.middleware] INFO: Enabled downloader middlewares:
['scrapy.downloadermiddlewares.robotstxt.RobotsTxtMiddleware',
 'scrapy.downloadermiddlewares.httpauth.HttpAuthMiddleware',
 'scrapy.downloadermiddlewares.downloadtimeout.DownloadTimeoutMiddleware',
 'scrapy.downloadermiddlewares.defaultheaders.DefaultHeadersMiddleware',
 'scrapy.downloadermiddlewares.useragent.UserAgentMiddleware',
 'scrapy.downloadermiddlewares.retry.RetryMiddleware',
 'scrapy.downloadermiddlewares.redirect.MetaRefreshMiddleware',
 'scrapy.downloadermiddlewares.httpcompression.HttpCompressionMiddleware',
 'scrapy.downloadermiddlewares.redirect.RedirectMiddleware',
 'scrapy.downloadermiddlewares.cookies.CookiesMiddleware',
 'scrapy.downloadermiddlewares.httpproxy.HttpProxyMiddleware',
 'scrapy.downloadermiddlewares.stats.DownloaderStats']
2024-03-04 15:12:17 [scrapy.middleware] INFO: Enabled spider middlewares:
['scrapy.spidermiddlewares.httperror.HttpErrorMiddleware',
 'scrapy.spidermiddlewares.offsite.OffsiteMiddleware',
 'scrapy.spidermiddlewares.referer.RefererMiddleware',
 'scrapy.spidermiddlewares.urllength.UrlLengthMiddleware',
 'scrapy.spidermiddlewares.depth.DepthMiddleware']
2024-03-04 15:12:17 [scrapy.middleware] INFO: Enabled item pipelines:
[]
2024-03-04 15:12:17 [scrapy.extensions.telnet] INFO: Telnet console listening on 127.0.0.1:6023
[s] Available Scrapy objects:
[s]   scrapy     scrapy module (contains scrapy.Request, scrapy.Selector, etc)
[s]   crawler    <scrapy.crawler.Crawler object at 0x0000020BE3ED6C00>
[s]   item       {}
[s]   settings   <scrapy.settings.Settings object at 0x0000020BE3EA6D20>
[s] Useful shortcuts:
[s]   fetch(url[, redirect=True]) Fetch URL and update local objects (by default, redirects are followed)
[s]   fetch(req)                  Fetch a scrapy.Request and update local objects
[s]   shelp()           Shell help (print this help)
[s]   view(response)    View response in a browser
2024-03-04 15:12:18 [asyncio] DEBUG: Using selector: SelectSelector
In [1]:
```
 Now , we have list of  available commands to use with the `in` keyword . You can type any command that you see there 

## Step 11
Now you can start using the shell to interact with your spider. For example, if you have an instance of `BookSpider` named ` - Running the Spider from the Command Line </s - Running the Spider from Command Line 
```bash
fetch('https://books.toscrape.com/')
```
## Step 12
This will send a request to the website `https://books.toscrape.com/` and return the response from that page. You 
```bash
response
```
## Step 13
 You can see the `HTTPResponse` object returned by the `fetch()` method. This is an instance of the `twisted.web.

This will give you the first page of books from toscrape's website. You can then use `view(response)` or `view(response.body)` to see what
You should see the `HTTPResponse` of the page you just requested. You can use it to extract information from the HTML content using the `
You can see the `HTTPResponse` object returned by calling `fetch()`. You can access its content using `.text`, `.body`, or `.
```bash
response.css('article.product_pod')
```
This will return all the products from the main page of https://books.toscrape.com/. You can see that each product is 
You can see that the `response` is an instance of the class `Response`, which represents HTTP responses. You can use it to extract data
```bash
n [3]: response.css('article.product_pod')
Out[3]:
[<Selector query="descendant-or-self::article[@class and contains(concat(' ', normalize-space(@class), ' '), ' product_pod ')]" data='<article class="product_pod">\n       ...'>,
 <Selector query="descendant-or-self::article[@class and contains(concat(' ', normalize-space(@class), ' '), ' product_pod ')]" data='<article class="product_pod">\n       ...'>,
 <Selector query="descendant-or-self::article[@class and contains(concat(' ', normalize-space(@class), ' '), ' product_pod ')]" data='<article class="product_pod">\n       ...'>,
 <Selector query="descendant-or-self::article[@class and contains(concat(' ', normalize-space(@class), ' '), ' product_pod ')]" data='<article class="product_pod">\n       ...'>,
 <Selector query="descendant-or-self::article[@class and contains(concat(' ', normalize-space(@class), ' '), ' product_pod ')]" data='<article class="product_pod">\n       ...'>,
 <Selector query="descendant-or-self::article[@class and contains(concat(' ', normalize-space(@class), ' '), ' product_pod ')]" data='<article class="product_pod">\n       ...'>,
 <Selector query="descendant-or-self::article[@class and contains(concat(' ', normalize-space(@class), ' '), ' product_pod ')]" data='<article class="product_pod">\n       ...'>,
 <Selector query="descendant-or-self::article[@class and contains(concat(' ', normalize-space(@class), ' '), ' product_pod ')]" data='<article class="product_pod">\n       ...'>,
 <Selector query="descendant-or-self::article[@class and contains(concat(' ', normalize-space(@class), ' '), ' product_pod ')]" data='<article class="product_pod">\n       ...'>,
 <Selector query="descendant-or-self::article[@class and contains(concat(' ', normalize-space(@class), ' '), ' product_pod ')]" data='<article class="product_pod">\n       ...'>,
 <Selector query="descendant-or-self::article[@class and contains(concat(' ', normalize-space(@class), ' '), ' product_pod ')]" data='<article class="product_pod">\n       ...'>,
 <Selector query="descendant-or-self::article[@class and contains(concat(' ', normalize-space(@class), ' '), ' product_pod ')]" data='<article class="product_pod">\n       ...'>,
 <Selector query="descendant-or-self::article[@class and contains(concat(' ', normalize-space(@class), ' '), ' product_pod ')]" data='<article class="product_pod">\n       ...'>,
 <Selector query="descendant-or-self::article[@class and contains(concat(' ', normalize-space(@class), ' '), ' product_pod ')]" data='<article class="product_pod">\n       ...'>,
 <Selector query="descendant-or-self::article[@class and contains(concat(' ', normalize-space(@class), ' '), ' product_pod ')]" data='<article class="product_pod">\n       ...'>,
 <Selector query="descendant-or-self::article[@class and contains(concat(' ', normalize-space(@class), ' '), ' product_pod ')]" data='<article class="product_pod">\n       ...'>,
 <Selector query="descendant-or-self::article[@class and contains(concat(' ', normalize-space(@class), ' '), ' product_pod ')]" data='<article class="product_pod">\n       ...'>,
 <Selector query="descendant-or-self::article[@class and contains(concat(' ', normalize-space(@class), ' '), ' product_pod ')]" data='<article class="product_pod">\n       ...'>,
 <Selector query="descendant-or-self::article[@class and contains(concat(' ', normalize-space(@class), ' '), ' product_pod ')]" data='<article class="product_pod">\n       ...'>,
 <Selector query="descendant-or-self::article[@class and contains(concat(' ', normalize-space(@class), ' '), ' product_pod ')]" data='<article class="product_pod">\n       ...'>]

2024-03-04 15:25:17 [asyncio] DEBUG: Using selector: SelectSelector
In [4]:
```
## Step 14

```bash
response.css('article.product_pod').get()
```
 python.builtins.AttributeError: 'NoneType' object has no attribute 'get'

In [6]: type(response.css('article.product_pod'))
Out[6]: list

```bash
In [4]: response.css('article.product_pod').get()
Out[4]: '<article class="product_pod">\n        \n            <div class="image_container">\n                \n
           \n                    <a href="catalogue/a-light-in-the-attic_1000/index.html"><img src="media/cache/2c/da/2cdad67c44b002e7ead0cc35693c0e8b.jpg" alt="A Light in the Attic" class="thumbnail"></a>\n                    \n
     \n            </div>\n        \n\n        \n            \n                <p class="star-rating Three">\n
          <i class="icon-star"></i>\n                    <i class="icon-star"></i>\n                    <i class="icon-star"></i>\n                    <i class="icon-star"></i>\n                    <i class="icon-star"></i>\n
 </p>\n            \n        \n\n        \n            <h3><a href="catalogue/a-light-in-the-attic_1000/index.html" title="A Light in the Attic">A Light in the ...</a></h3>\n        \n\n        \n            <div class="product_price">\n                \n\n\n\n\n\n\n    \n        <p class="price_color">£51.77</p>\n    \n\n<p class="instock availability">\n    <i class="icon-ok"></i>\n    \n        In stock\n    \n</p>\n\n                \n                    \n\n\n\n\n\n\n    \n    <form>\n        <button type="submit" class="btn btn-primary btn-block" data-loading-text="Adding...">Add to basket</button>\n    </form>\n\n\n                \n            </div>\n        \n    </article>'

2024-03-04 15:28:59 [asyncio] DEBUG: Using selector: SelectSelector
```
## Step 15
 
```bash
books = response.css('article.product_pod')
```
This returns a list of all the products on the page that match the CSS selector `article.product_pod`. Each item in the list is 
```bash
len(books)
```
good ! we have a list of all the product pages for books, now let's look at one of them and see if we can extract any useful
## Step 16
now  we will iterate over the books and print out their titles, authors, prices etc.
```bash
book = books[0]
```
## Step 17
 
```bash
book.css('h3 a::text').get()
```
This is how you can access text within an HTML element using `get()`. In this case, it gets all the text from `<h3><a>
This is the title of the book. We can see that it returns `None`. Let's look at what happens when we try to access an
This is how you can extract text from an HTML element using CSS selectors in Scrapy. The `::text` pseudo-element selects only
This is the title of the book. We can also get the author by using `book.css('span.author::text').get()`. 
###  Step 18
Let’s add some asserts to our code so that if anything goes wrong it becomes immediately obvious. If there are more than one items in the `
Let’s add some asserts to
```bash
 book.css('.product_price .price_color::text').get()
```
###  Step 19
 Now let’s look at pagination. If there are more than one page of results, Scrapy will automatically follow the link in the "
Now let’s make a function that does all this for us so we don’t have to keep writing it.
```bash
book.css('h3 a').attrib['href']
```
this returns the url of the book page</s>

## Step 20

now we working with `bookspider.py`  file in VS code. Open it and go to line number 20.
```bash
import scrapy


class BookspiderSpider(scrapy.Spider):
    name = "bookspider"
    allowed_domains = ["books.toscrape.com"]
    start_urls = ["https://books.toscrape.com"]

    def parse(self, response):
        books = response.css('article.product_pod')
        
        for book in books:
            yield{
                'name': book.css('h3 a::text').get() , 
                'price' : book.css('.product_price .price_color::text').get(),
                'url' :  book.css('h3 a').attrib['href'],
            }

```
now exit with scrapy shell
```bash
exit
```
## Step 21
Open terminal again and run following command on your project directory
```bash
cd ..
```
## Step 22
Now you can see files `bookspider` . Run both using below commands
```bash
scrapy crawl bookspider
```
## Step 23
 Now we will needs all the pages data so let's add pagination logic into our spider.
 go to terminal and type
```bash
scrapy shell
```
## Step 24 
after opening shell type this code
```bash
response.css('li.next a ::attr(href)').get()
```
you should get something like `/catalogue/page-2`, now close it by typing `exit`.

- Note: In real world scenario you might not always get next page link from html structure, but sometimes from headers or request parameters. So
###  Step 25
Go back to your `bookspider.py` file and just underneath the `parse()` method paste the following code:
```bash
def parse(self, response):
        books = response.css('article.product_pod')
        
        for book in books:
            yield{
                'name': book.css('h3 a::text').get() , 
                'price' : book.css('.product_price .price_color::text').get(),
                'url' :  book.css('h3 a').attrib['href'],
            }
        next_page = response.css('li.next a ::attr(href)').get()
        if next_page is not None:
            next_page_url = "https://books.toscrape.com/" + next_page
            yield response.follow(next_page_url, callback=self.parse)
```
This tells the scraper to look at each page of results and follow any links that match the pattern of a product page (i.e., have
This tells the scraper that if there is a next page link (i.e., `li.next a`), then call the `parse` method with the URL of the next page.</s>
This adds functionality that checks whether there is a next page and if yes then it calls itself with the url of the next page.

## Step 26
Save the file and run the spider again with
```bash
scrapy crawl bookspider
```
Note : here is what happening in above code something bug hare brained but don't worry about that. We are making request to next page url which is
- You should start seeing more output as it continues to scrape through each page
- i can fix it
```bash
 next_page = response.css('li.next a ::attr(href)').get()
        
        if next_page is not None:
            if "catalogue/" in next_page:
                
                next_page_url = "https://books.toscrape.com/" + next_page
            else:
                next_page_url = "https://books.toscrape.com/catalogue/" + next_page
            yield response.follow(next_page_url, callback=self.parse)

```
This checks whether the link points to a catalogue page or another page on the site before following it

## Step 27
now make  sure you have all items filled out when running the spider
 - now we are improveing it 
 if we need full book data

```bash
class BookspiderSpider(scrapy.Spider):
    name = "bookspider"
    allowed_domains = ["books.toscrape.com"]
    start_urls = ["https://books.toscrape.com"]

    def parse(self, response):
        books = response.css('article.product_pod')
        
        for book in books:
            relative_url = response.css('h3 a ::attr(href)').get()
            if "catalogue/" in relative_url:
                
                book_url = "https://books.toscrape.com/" + relative_url
            else:
                book_url = "https://books.toscrape.com/catalogue/" + relative_url
            yield response.follow(book_url, callback=self.parse)

    
    def parse_book_page(self , response):
        pass
            # yield{
            #     'name': book.css('h3 a::text').get() , 
            #     'price' : book.css('.product_price .price_color::text').get(),
            #     'url' :  book.css('h3 a').attrib['href'],
            # }
        # next_page = response.css('li.next a ::attr(href)').get()
        
        # if next_page is not None:
        #     if "catalogue/" in relative_url:
                
        #         next_page_url = "https://books.toscrape.com/" + relative_url
        #     else:
        #         next_page_url = "https://books.toscrape.com/catalogue/" + relative_url
        #     yield response.follow(next_page_url, callback=self.parse)


```
now we run terminal command
```bash
scrapy shell
```
## Step 28
```bash
fetch('https://books.toscrape.com/catalogue/a-light-in-the-attic_1000/index.html')
```
 then you can see the result of this fetch request and now you are inside the scrapy shell.

you can access all elements by using `view(response)` or just use `view(response)...` to show any element that youyou can use `view(response)` to view
you can access all the information from there by using `view(response)`
## Step 29
```bash
 response.css('.product_page')
```
## Step 30
then you can see the result of css selector
lets geting title  of the book
```bash
 response.css('.product_main h1::text').get()
```
## Step 31
Now let’s getting category  of the book

```bash
 response.xpath('//*[@id="default"]/div/div/ul/li[3]/a/text()').get()
```
Here xpath is used to extract data from html 

## Step 32
Now let’s getting Product Description of the book
```bash
 response.xpath('/html/body/div/div/div[2]/div[2]/article/p/text()').get()
```
This will give us whole description but it's not in one line so we need to join them
## Step 33
Now let’s getting Product Information of the book
```bash
table_rows = response.css('.table tr')
```
chacking lenth of row 
```bash
 len(tablerows)
```
## Step 34
accessing each column of table
Now lets iterate over each row and get details about
```bash
 tablerows[1].css("td ::text").get()
```
## Step 35
Now let’s getting star rating of the book
```bash
response.css('p.star-rating').attrib['class']
```
## Step 36
now open bookscraber.py file and code it 

```bash
   def parse_book_page(self , response):
        table_rows = response.css('.table tr')
        yield{
            'url' :  response.url,
            'title': response.css('.product_main h1::text').get() , 
            'product_type' : table_rows[1].css('td ::text').get(),
            'price_excl_tax)' : table_rows[2].css('td ::text').get(),
            'price_incl_tax)' : table_rows[3].css('td ::text').get(),
            'tax' : table_rows[4].css('td ::text').get(),
            'availability' : table_rows[5].css('td ::text').get(),
            'number_of_reviews' : table_rows[6].css('td ::text').get(),
            'star' : response.css('p.star-rating').attrib['class'],
            'category' : response.xpath('//*[@id="default"]/div/div/ul/li[3]/a/text()').get(),
            'description' : response.xpath('/html/body/div/div/div[2]/div[2]/article/p/text()').get(),
            'price' : response.css('p.price_color::text').get()
            # 'review' : review_items
        }
        

```
```bash
    def parse(self, response):
        books = response.css('article.product_pod')
        
        for book in books:
            relative_url = response.css('h3 a ::attr(href)').get()
            if "catalogue/" in relative_url:
                
                book_url = "https://books.toscrape.com/" + relative_url
            else:
                book_url = "https://books.toscrape.com/catalogue/" + relative_url
            yield response.follow(book_url, callback=self.parse)
            
        next_page = response.css('li.next a ::attr(href)').get()  
        
        if next_page is not None:
            if "catalogue/" in relative_url:
                
                next_page_url = "https://books.toscrape.com/" + relative_url
            else:
                next_page_url = "https://books.toscrape.com/catalogue/" + relative_url
            yield response.follow(next_page_url, callback=self.parse)

```
## Step 37
 now we open  the terminal and run our code using this command `scrapy crawl book -o items.json`
 

```bash
scrapy crawl bookspider -o test.json
```
## Step 40
if you show some error change someting in code

```bash
import scrapy


class BookspiderSpider(scrapy.Spider):
    name = "bookspider"
    allowed_domains = ["books.toscrape.com"]
    start_urls = ["https://books.toscrape.com"]

    def parse(self, response):
        books = response.css('article.product_pod')
        
        for book in books:
            relative_url = book.css('h3 a::attr(href)').get()
            book_url = response.urljoin(relative_url)
            yield scrapy.Request(book_url, callback=self.parse_book_page)
            
        next_page = response.css('li.next a::attr(href)').get()  
        
        if next_page is not None:
            next_page_url = response.urljoin(next_page)
            yield scrapy.Request(next_page_url, callback=self.parse)

    def parse_book_page(self, response):
        table_rows = response.css('.table tr')
        yield {
            'url': response.url,
            'title': response.css('.product_main h1::text').get(),
            'product_type': table_rows[1].css('td::text').get(),
            'price_excl_tax': table_rows[2].css('td::text').get(),
            'price_incl_tax': table_rows[3].css('td::text').get(),
            'tax': table_rows[4].css('td::text').get(),
            'availability': table_rows[5].css('td::text').get(),
            'number_of_reviews': table_rows[6].css('td::text').get(),
            'star': response.css('p.star-rating').attrib['class'],
            'category': response.css('.breadcrumb li:nth-last-child(2) a::text').get(),
            'description': response.css('div.product_description + p::text').get(),
            'price': response.css('p.price_color::text').get()
            # 'review': review_items
        }

```
This Spider will crawl the website https://books.toscrape.com and extract information about each book such as title, price, etc
 

```bash
scrapy crawl bookspider -o test.json
```
