# **South Wales Fitness Testing**
[Back to README](README.md)

# **Contents**

* **[HTML](#html)**
  * [index.html](#index.html)
  * [classes.html](#classes.html)
  * [information.html]()
  * [pricing.html]()
* **[CSS]()**


# **HTML**

## Index.html
Initial check for errors in code done using [W3C Markup Validation Service](https://validator.w3.org/)

* `` img `` tag missing ``src``
  * This was due to chaning the ``src`` to ``data-src`` and not adding it as a new attribute instead. - All ``img`` tags had the src attribute added which fixed the error.

The page was then checked for spelling mistakes using [typosaurus](https://typosaur.us/)

---

I then moved on to test with [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/) this came back with the following audit points that needed to be addressed.

### **Mobile**
Initial score 71/100

#### **Lab Data**
* First Contentful Paint - 2.8s (high)
* Time to Interactive - 2.8s (good)
* Speed Index - 2.8s (good)
* Total Blocking Time - 0ms (good)
* Largest Contentful Paint - 10.5s (high)
* Cumulative Layout Shift 0.018 (good)

**Opportunities Identified**
* Properly size images - Estimated saving 24.15s
  * This recommended that I use multiple images to save load times on images. I tested this by using the [ImageMagick CLI](https://www.imagemagick.org/script/index.php) to resize and then using `srcset` property on the images but I was unable to get this to properly function and due to time restrictions on the project I had decided to leave this to be revisited in future to implement.
* Eliminate render-blocking resources - Estimated saving 1.94s
  * This was showing that the bootstrap and FA CDN scripts should be loaded with async or defer but due to the importance of the two and errors caused by using these with either of the two I am unable to resolve this issue.
* Remove unused CSS - estimated saving 0.3s
  * This was showing that the CSS files from bootstrap and FontAwesome were not used, but the classes and styling from both of these are used consistanely throughout this page so they cannot be removed.

**Diagnostics**
* Serve static assets with an efficient cache policy
  * This recommended that the cache-control be increased to speed up multipl visits. After researching into this I found [this artice](https://webapps.stackexchange.com/questions/119286/caching-assets-in-website-served-from-github-pages) which shows that due to the deployment on GitHub Pages it is not possible to increase this. I am unable to resolve this with the current resources and skillset.
* Reduce the impact of third-party code
  * This recommended that the third-party scripts that are delivered through the CDN's be loaded either using async or defer. As the scripts that are used should not be classed as third-party due to them being essential content for the website this cannot be done at this time.
* Image elements do not have explicit width and height
  * This is the same as the "Properly size images" in the opportunities, so again I have decided that this is not currently something that I can implement and it will be revisited at a later date.
* Avoid enormous network payloads
  * Lazyload was added to the webpage to reduce the amount of data required when loading images.
* Minimize main-thread work
  * This is in relation to the JS files that are linked with the project, unfortunately at this time I have not developed any JS files and this is only in relation to the frameworks that I have loaded, which cannot be changed by myself.

### **Desktop**
Initial score 91/100

#### **Lab Data**
* First Contentful Paint - 0.8s (good)
* Time to Interactive - 0.8s (good)
* Speed Index - 0.8s (good)
* Total Blocking Time - 0ms (good)
* Largest Contentful Paint - 1.9s (high)
* Cumulative Layout Shift 0.002 (good)

**Opportunities Identified**
* Properly size images - Estimated saving 3.98s
  * As with the testing in the mobile section, I tried to follow the suggestions and the documentation that was provided but at this time I was unable to resolve the issue.
* Eliminate render-blocking resources - Estimated saving 0.53s
  * This is also the same as the issue with the mobile section so cannot be resolved as the scripts identified are needed for the site.d.

**Diagnostics**
* Serve static assets with an efficient cache policy
  * This recommended that the cache-control be increased to speed up multipl visits. After researching into this I found [this artice](https://webapps.stackexchange.com/questions/119286/caching-assets-in-website-served-from-github-pages) which shows that due to the deployment on GitHub Pages it is not possible to increase this. I am unable to resolve this with the current resources and skillset.
* Image elements do not have explicit width and height
  * This is the same as the "Properly size images" in the opportunities, so again I have decided that this is not currently something that I can implement and it will be revisited at a later date.
* Avoid enormous network payloads
  * Lazyload was added to the webpage to reduce the amount of data required when loading images.

  ---

**Browser testing**

I tested the index page across FireFox, Brave, Google Chrome, Edge, Opera, and vivaldi that are all installed on my computer and then Safari from my iPhone.

When testing it was noticed that the images did not render as nicely in the other browsers on mobile as it did in the development browser (FireFox) to fix this I applied a general rule to all `img` tags site wide to apply an image-rendering property that would better render the images.

I had also found that I had used the `col-sm-*` class instead of `col-*` on the testimonials section which meant that below 576px it did not perform as expected, this was fixed by changing the class used.

## Classes.html

Initial check for errors in code done using [W3C Markup Validation Service](https://validator.w3.org/)

* Start tag ``<span>`` seen in table.
  * Initially this was used for accessibility reasons as I did not want to use a caption over the top of the timetable. After reading this article by [WebAIM](https://webaim.org/techniques/tables/data) I amended all of the table elements to have the scope added to all ``<th> `` elements in the tables. - this resolved the issue.
* `` img `` tag missing ``src``
  * This was due to chaning the ``src`` to ``data-src`` and not adding it as a new attribute instead. - All ``img`` tags had the src attribute added which fixed the error.

The page was then checked for spelling mistakes using [typosaurus](https://typosaur.us/)

---

I then moved on to test with [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/) this came back with the following audit points that needed to be addressed.

### **Mobile**
Initial score 71/100

#### **Lab Data**
* First Contentful Paint - 2.8s (high)
* Time to Interactive - 2.8s (good)
* Speed Index - 2.8s (good)
* Total Blocking Time - 0ms (good)
* Largest Contentful Paint - 10.5s (high)
* Cumulative Layout Shift 0.018 (good)

**Opportunities Identified**
* Properly size images - Estimated saving 24.15s
  * This recommended that I use multiple images to save load times on images. I tested this by using the [ImageMagick CLI](https://www.imagemagick.org/script/index.php) to resize and then using `srcset` property on the images but I was unable to get this to properly function and due to time restrictions on the project I had decided to leave this to be revisited in future to implement.
* Eliminate render-blocking resources - Estimated saving 1.94s
  * This was showing that the bootstrap and FA CDN scripts should be loaded with async or defer but due to the importance of the two and errors caused by using these with either of the two I am unable to resolve this issue.
* Remove unused CSS - estimated saving 0.3s
  * This was showing that the CSS files from bootstrap and FontAwesome were not used, but the classes and styling from both of these are used consistanely throughout this page so they cannot be removed.

**Diagnostics**
* Serve static assets with an efficient cache policy
  * This recommended that the cache-control be increased to speed up multipl visits. After researching into this I found [this artice](https://webapps.stackexchange.com/questions/119286/caching-assets-in-website-served-from-github-pages) which shows that due to the deployment on GitHub Pages it is not possible to increase this. I am unable to resolve this with the current resources and skillset.
* Reduce the impact of third-party code
  * This recommended that the third-party scripts that are delivered through the CDN's be loaded either using async or defer. As the scripts that are used should not be classed as third-party due to them being essential content for the website this cannot be done at this time.
* Image elements do not have explicit width and height
  * This is the same as the "Properly size images" in the opportunities, so again I have decided that this is not currently something that I can implement and it will be revisited at a later date.
* Avoid enormous network payloads
  * Lazyload was added to the webpage to reduce the amount of data required when loading images.
* Minimize main-thread work
  * This is in relation to the JS files that are linked with the project, unfortunately at this time I have not developed any JS files and this is only in relation to the frameworks that I have loaded, which cannot be changed by myself.

### **Desktop**
Initial score 91/100

#### **Lab Data**
* First Contentful Paint - 0.8s (good)
* Time to Interactive - 0.8s (good)
* Speed Index - 0.8s (good)
* Total Blocking Time - 0ms (good)
* Largest Contentful Paint - 1.9s (high)
* Cumulative Layout Shift 0.002 (good)

**Opportunities Identified**
* Properly size images - Estimated saving 3.98s
  * As with the testing in the mobile section, I tried to follow the suggestions and the documentation that was provided but at this time I was unable to resolve the issue.
* Eliminate render-blocking resources - Estimated saving 0.53s
  * This is also the same as the issue with the mobile section so cannot be resolved as the scripts identified are needed for the site.d.

**Diagnostics**
* Serve static assets with an efficient cache policy
  * This recommended that the cache-control be increased to speed up multipl visits. After researching into this I found [this artice](https://webapps.stackexchange.com/questions/119286/caching-assets-in-website-served-from-github-pages) which shows that due to the deployment on GitHub Pages it is not possible to increase this. I am unable to resolve this with the current resources and skillset.
* Image elements do not have explicit width and height
  * This is the same as the "Properly size images" in the opportunities, so again I have decided that this is not currently something that I can implement and it will be revisited at a later date.
* Avoid enormous network payloads
  * Lazyload was added to the webpage to reduce the amount of data required when loading images.

  ---

**Browser testing**

I tested the index page across FireFox, Brave, Google Chrome, Edge, Opera, and vivaldi that are all installed on my computer and then Safari from my iPhone.

When testing it was noticed that the images did not render as nicely in the other browsers on mobile as it did in the development browser (FireFox) to fix this I applied a general rule to all `img` tags site wide to apply an image-rendering property that would better render the images.

I had also found that I had used the `col-sm-*` class instead of `col-*` on the testimonials section which meant that below 576px it did not perform as expected, this was fixed by changing the class used.