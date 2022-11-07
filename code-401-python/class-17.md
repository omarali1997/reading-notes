# Read 17 : Automation
> # Automation
### Automation: a process in which a manually performed action is transformed into one that happens automatically.

<img src="https://images.unsplash.com/photo-1518432031352-d6fc5c10da5a?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1934&q=80">

### The process of automating a task is one in which a framework is activated. This framework, for our purposes a programming script, makes it possible for the task to be performed autonomously, on its own, without user intervention.

## Why would someone choose to automate a task? There are two main reasons.

## 1. Automating a task means that it can run a lot quicker, most of the time.

## 2. Automating a task means there’s less potential for mistakes, as the impact of human error is mitigated.


># Python Automation Ideas
### There are a huge range of tasks that you might opt to automate by writing Python scripts. Python users can use their creativity to create innovative automated solutions for the boring stuff they encounter in their daily life.

### To give you an idea of the breadth of how users utilize Python to automate tasks, here are some common ways that Python automation is used:

>## Sending out, replying to, and sorting emails
### Python uses Simple Mail Transfer Protocol (SMTP) which is the communication protocol used by all email systems. Python’s library provides the smptlib module built-in so there’s no need for installation. Once connected to a mail server, you can specify the sender and receiver of the email, and input all the email text.

>## Filling out PDFs and Excel files
### Form fields can be easily filled using the pdfrw library which can read and write PDF files. Once the PDF template is connected, you can grab the keys for each form field in the PDF and assign values to each key to automatically fill out online forms.

>## Sending HTTP requests
### There are many Python libraries used to make HTTP requests. Requests is one of the most popular and user-friendly libraries. From the requests library, you can use GET and POST Python scripts to request and send data to and from a server.

>## Converting image files

### The pillow module allows users to import images using the Python Image Library (PIL). The save() method can be used along with a specified format to save an uploaded image in the format of your choice.



>## Performing quick math equations

### Python can be used to define equations using SymPy and math variables. Unlike expressions, which are just a collection of symbols and operators, equations have equality. Essentially, the expression used in the code will be equal to something else, which allows for more complex math equations.



>## Calculating exchange rates

### Python can provide direct currency exchange rates using the forex-python module. The module includes functions and parameters that can be used to input the currency for exchange. Once the currency exchange values are imported, the module will output the real-time currency exchange value.



>## Scraping data from web pages and saving it in the harddrive

### Python features many modules that can effectively scrape data from web pages. One example is the BeautifulSoup library, which can extract data from HTML and XML files. You can specify the data you would like extracted from a web page depending on your use cases. Common use cases of web scraping include comparing prices between products, collecting email addresses, and collecting job listings.


### Python code can be used to automate a whole ton more. Think of the tasks you perform dozens of times a day: copy and pasting things from one document to another, multiplying numbers by 100, or whatever else. These tasks can be automated by Python; you just have to figure out what tools you’ll need, and how you can write and run Python scripts.


>## Examples of Python Scripts for Automation

### Here is an example of a simple Python script with different methods that calculate the power of a number by assigning values to expressions and operators. The script below will return 4 to the power of 3.

```python
import math
# Assign values to x and n
x = 4
n = 3



# Method 1
power = x ** n
print("%d to the power %d is %d" % (x,n,power))



# Method 2
power = pow(x,n)
print("%d to the power %d is %d" % (x,n,power))
```

### Another useful example is a Python script that automates the process of converting PNG images to JPEG format.



```python
import os
import sys
from PIL import Image

if len(sys.argv) > 1:
    if os.path.exists(sys.argv[1]):
        im = Image.open(sys.argv[1])
        target_name = sys.argv[1].split(".")[0] + ".jpg"
        rgb_im = im.convert('RGB')
        rgb_im.save(target_name)
        print("Saved as " + target_name)
    else:
        print(sys.argv[1] + " not found")
else:
    print("Usage: convert2jpg.py <file>")
```
### These are just a few examples of Python code snippets that can help automate simple, everyday tasks.


>## Python Automation Tools

### Because of its open source licensing, Python has an engaged, supportive developer community backing it up. This means that there’s a range of Python libraries, tools, and frameworks available to bolster your programming efforts. This is good news for both the aspiring software developer and those who just want to automate basic tasks as simply as possible.

### There are a bunch of tools you can use to make your automation efforts simpler and more intuitive. Dive into internet research to see what exactly is available to help you with the task you’re trying to automate, or lean into one of the many Python community forums for help.

### But for starters, let’s look at a few great tools that can help you with automation.

### The smtplib library is a great resource that will help you automate your emails. It uses the Simple Mail Transfer Protocol, which can be integrated easily with most major email platforms, like Gmail.

### Selenium is an open-source software tool that you can use to automate tests carried out in web browsers. This can test websites for bugs, site crashes, and related things. This can potentially save users tons of time, or save you from not realizing your website has gone offline.

### Beautiful Soup is a humorously named Python library that can be used to pull data out of HTML and XML files. Instead of manually going through a ton of HTML files and manually looking for the information you need, you can use this library to save you time and labour.

# Are you ready to do your own automations with Python?
 





