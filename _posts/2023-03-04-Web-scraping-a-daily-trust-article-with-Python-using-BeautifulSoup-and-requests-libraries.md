Web scraping is a key skill all data scientists should have. This is why day 22 of our ongoing Arewa Data Science Academy fellowship covered web scraping using BeautifulSoup. In this article, I try to explain and practice this important skill by scraping a daily trust [page](<https://dailytrust.com/last-saturday-polls-raised-issues-that-require-immediate-solutions-inec/>) that contains an article related to the just concluded Nigerian presidential election. 
Firstly, for this task, one needs the following:
- A Python installation -I have Python 3.10 installed, 
- requests [library](<https://docs.python-requests.org/en/v2.9.1/>)
- BeautifulSoup4 [library](<https://www.crummy.com/software/BeautifulSoup/bs4/doc/>)

Both libraries can be installed using pip, or if one uses a conda environment - like I do - the libraries can be installed using conda install <library_name>. In addition, the documentation for both libraries, which are hyperlinked above, provide description for how to install the libraries. 
For the purpose of this article, I used a colab Jupyter notebook, which is free from google and only requires a google account and an internet connection. There's no need to install anything else. 
We first begin by importing the two required libraries

![carbon](https://user-images.githubusercontent.com/110518958/222918210-eb2b9ba6-638b-4de1-ba92-e426d3fb7c45.png)

Requests library enables us to get the content of the page as a html and BeautifulSoup allows us to parse the html. 
We then create a beautifulSoup object that we can use to navigate the content of the page as follows:
![carbon (1)](https://user-images.githubusercontent.com/110518958/222918278-c8a7c087-d366-4305-90ec-bcbbb8cead0c.png)

The url of the page is first declared, then the response object is created using the get method of requests. Afterwards, the content attribute of the response object is passed to BeautifulSoup to create a soup object that we can use to navigate through the content of the web page. The prettify method is used to show the basic structure of the web page as this can help in pinpointing the exact content needed, in our case, the paragraphs. 

To keep things simple for now, this is the approach I followed:

![carbon (5)](https://user-images.githubusercontent.com/110518958/222918392-57ff8ba0-ea50-4765-84af-f068b7a8fe60.png)

First, the find_all() method is used to get all the p tags as a list and this is assigned to the paragraphs variable. Then for the main target of this article, I print the title attribute of the soup object and then loop through each item in the paragraphs variable and print, this gives the entire content of the article. I discovered that the hyperlinked titles of related articles where included and I removed them by excluding all p tags that contained a tags. 

Below is the output, giving the complete text of the article:

![carbon (4)](https://user-images.githubusercontent.com/110518958/222918444-9859fdc9-8992-428e-b2ca-e75e2981b194.png)

In conclusion, web scraping is highly useful to a data scientist as it automates getting content from the internet. One does not have to cut and paste long pieces of text or other contents. The colab notebook that contains the code can be found [here](<https://colab.research.google.com/drive/1QjBNPFysYVV4MlSeT82SPiv2kuKbIWho?usp=sharing>).
