# read 14: Web Scraping
># Web Scraping 
### Web scraping is the process of collecting and parsing raw data from the Web, and the Python community has come up with some pretty powerful web scraping tools.

### The Internet hosts perhaps the greatest source of information on the planet. Many disciplines, such as data science, business intelligence, and investigative reporting, can benefit enormously from collecting and analyzing data from websites.



# Scrape and Parse Text From Websites
### Collecting data from websites using an automated process is known as web scraping. Some websites explicitly forbid users from scraping their data with automated tools like the ones that you’ll create in this tutorial. Websites do this for two possible reasons:

>## 1. The site has a good reason to protect its data. For instance, Google Maps doesn’t let you request too many results too quickly.
>## 2. Making many repeated requests to a website’s server may use up bandwidth, slowing down the website for other users and potentially overloading the server such that the website stops responding entirely.
## Before using your Python skills for web scraping, you should always check your target website’s acceptable use policy to see if accessing the website with automated tools is a violation of its terms of use. Legally, web scraping against the wishes of a website is very much a gray area.

#
## One useful package for web scraping that you can find in Python’s standard library is urllib, which contains tools for working with URLs. In particular, the urllib.request module contains a function called urlopen() that you can use to open a URL within a program.

>##  In IDLE’s interactive window, type the following to import urlopen():

```python
>>> from urllib.request import urlopen
```
## The web page that you’ll open is at the following URL:

```python
>>> url = "http://olympus.realpython.org/profiles/aphrodite"
```
## To open the web page, pass url to urlopen():

```python
>>> page = urlopen(url)
```
## urlopen() returns an HTTPResponse object:

```python
>>> page
<http.client.HTTPResponse object at 0x105fef820>
```
## To extract the HTML from the page, first use the HTTPResponse object’s `.read()` method, which returns a sequence of bytes. Then use `.decode()` to decode the bytes to a string using `UTF-8`:
```python
>>> html_bytes = page.read()
>>> html = html_bytes.decode("utf-8")
```
## Now you can `print` the HTML to see the contents of the web page:

```python
>>> print(html)
<html>
<head>
<title>Profile: Aphrodite</title>
</head>
<body bgcolor="yellow">
<center>
<br><br>
<img src="/static/aphrodite.gif" />
<h2>Name: Aphrodite</h2>
<br><br>
Favorite animal: Dove
<br><br>
Favorite color: Red
<br><br>
Hometown: Mount Olympus
</center>
</body>
</html>
```
## The output that you’re seeing is the HTML code of the website, which your browser renders when you visit http://olympus.realpython.org/profiles/aphrodite:

<img src="https://files.realpython.com/media/website_aphrodite.10b67047ebc2.png">

### With urllib, you accessed the website similarly to how you would in your browser. However, instead of rendering the content visually, you grabbed the source code as text. Now that you have the HTML as text, you can extract information from it in a couple of different ways.






