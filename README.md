# Mission-to-Mars
Practice and Challenge Assignment for Module 10

## Background
Robin's web app is looking good and functioning well, but she wants to add more polish to it. She had been admiring images of Mars’s hemispheres online and realized that the site is scraping-friendly. She would like to adjust the current web app to include all four of the hemisphere images. To do this, you’ll use BeautifulSoup and Splinter to scrape full-resolution images of Mars’s hemispheres and the titles of those images, store the scraped data on a Mongo database, use a web application to display the data, and alter the design of the web app to accommodate these images.

## Personal Commentary
I hope Robin doesn't mind the color scheme. I found that using the color names makes the custom.css file easier to read. While the Mission to Mars site's coloring does make it look a little archaic, especially on the table, I personally believe that it is still easy to read and easy on the eyes.

The biggest difficult in creating this website was troubleshooting the app. to make sure the scrape button worked and making sure that changes in the custom.css file are reflected on the website.


The first problem was solved by fixing a slight typo on line 20 of the app.py. 

My line had read:

```
mars.update({}, {"$set":mars_data}, upsert=True)
```

When it was supposed to be:

```
mars.update_one({}, {"$set":mars_data}, upsert=True)
```

The issue with .update was because the Mars variable is a collection object, there is no .update method for it. If I did not use the .update_one, I would receive this error on my terminal.

```
TypeError: 'Collection' object is not callable. If you meant to call the 'update' method on a 'Collection' object it is failing because no such method exists.
```


The second issue with the CSS took a little more research. I found out that I would have to refresh my cached page by using CTRL + F5. This forced the cache to refresh and allowed the changes on my custom.css file to be reflected on the Mission to Mars website.

Thanks to this, my site went from looking like the example on the module:

![Original Site](https://github.com/Itgotworse26/Mission-to-Mars/blob/main/Mission_to_Mars_Site_Original.PNG)

To looking like this:

![New Site](https://github.com/Itgotworse26/Mission-to-Mars/blob/main/Mission_to_Mars_Site_Revision.PNG)