# **South Wales Fitness Testing**
[Back to README](README.md)

# **Contents**
* **[HTML](#html)**
  * [index.html](#index.html)
  * [classes.html](#classes.html)
  * [information.html](#information.html)
  * [pricing.html](#pricing.html)
  * [404.html](#404.html)
* **[CSS](#css)**
  * [style.css](#style.css)
  * [utilities.css](#utilities.css)


# **HTML**
## **Index.html**
Initial check for errors in code done using [W3C Markup Validation Service](https://validator.w3.org/)

* `` img `` tag missing ``src``
  * This was due to changing the ``src`` to ``data-src`` and not adding it as a new attribute instead. - All ``img`` tags had the src attribute added which fixed the error.

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
  * This was showing that the CSS files from bootstrap and FontAwesome were not used, but the classes and styling from both of these are used consistently throughout this page so they cannot be removed.

**Diagnostics**
* Serve static assets with an efficient cache policy
  * This recommended that the cache-control be increased to speed up multiple visits. After researching into this I found [this article](https://webapps.stackexchange.com/questions/119286/caching-assets-in-website-served-from-github-pages) which shows that due to the deployment on GitHub Pages it is not possible to increase this. I am unable to resolve this with the current resources and skill set.
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
  * This is also the same as the issue with the mobile section so cannot be resolved as the scripts identified are needed for the site

**Diagnostics**
* Serve static assets with an efficient cache policy
  * This recommended that the cache-control be increased to speed up multiple visits. After researching into this I found [this article](https://webapps.stackexchange.com/questions/119286/caching-assets-in-website-served-from-github-pages) which shows that due to the deployment on GitHub Pages it is not possible to increase this. I am unable to resolve this with the current resources and skill set.
* Image elements do not have explicit width and height
  * This is the same as the "Properly size images" in the opportunities, so again I have decided that this is not currently something that I can implement and it will be revisited at a later date.
* Avoid enormous network payloads
  * Lazyload was added to the webpage to reduce the amount of data required when loading images.

---

**Browser testing**
I tested the index page across FireFox, Brave, Google Chrome, Edge, Opera, and vivaldi that are all installed on my computer and then Safari from my iPhone.

When testing it was noticed that the images did not render as nicely in the other browsers on mobile as it did in the development browser (FireFox) to fix this I applied a general rule to all `img` tags site wide to apply an image-rendering property that would better render the images.

I had also found that I had used the `col-sm-*` class instead of `col-*` on the testimonials section which meant that below 576px it did not perform as expected, this was fixed by changing the class used.

[Back to index](#contents)

---

## **Classes.html**
Initial check for errors in code done using [W3C Markup Validation Service](https://validator.w3.org/)

* Start tag ``<span>`` seen in table.
  * Initially this was used for accessibility reasons as I did not want to use a caption over the top of the timetable. After reading this article by [WebAIM](https://webaim.org/techniques/tables/data) I amended all of the table elements to have the scope added to all ``<th> `` elements in the tables. - this resolved the issue.
* `` img `` tag missing ``src``
  * This was due to changing the ``src`` to ``data-src`` and not adding it as a new attribute instead. - All ``img`` tags had the src attribute added which fixed the error.
* ``aria-controls`` were mislabelled - these were changed to the correct attributes.

The page was then checked for spelling mistakes using [typosaurus](https://typosaur.us/)

---

I then moved on to test with [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/) this came back with the following audit points that needed to be addressed.

### **Mobile**
Initial score 87/100

#### **Lab Data**
* First Contentful Paint - 2.9s (high)
* Time to Interactive - 2.9s (good)
* Speed Index - 2.9s (good)
* Total Blocking Time - 0ms (good)
* Largest Contentful Paint - 3.4s (high)
* Cumulative Layout Shift 0.002 (good)

**Opportunities Identified**
* Properly size images - Estimated saving 56.37s
  * This recommended that I use multiple images to save load times on images. I tested this by using the [ImageMagick CLI](https://www.imagemagick.org/script/index.php) to resize and then using `srcset` property on the images but I was unable to get this to properly function and due to time restrictions on the project I had decided to leave this to be revisited in future to implement.
* Eliminate render-blocking resources - Estimated saving 1.9s
  * This was showing that the bootstrap and FA CDN scripts should be loaded with async or defer but due to the importance of the two and errors caused by using these with either of the two I am unable to resolve this issue.
* Remove unused CSS - estimated saving 0.15s
  * This was showing that the CSS files from bootstrap and FontAwesome were not used, but the classes and styling from both of these are used consistently throughout this page so they cannot be removed.

**Diagnostics**
* Avoid enormous network payloads
  * Lazyload was added to the webpage to reduce the amount of data required when loading images.
* Serve static assets with an efficient cache policy
  * This recommended that the cache-control be increased to speed up multiple visits. After researching into this I found [this article](https://webapps.stackexchange.com/questions/119286/caching-assets-in-website-served-from-github-pages) which shows that due to the deployment on GitHub Pages it is not possible to increase this. I am unable to resolve this with the current resources and skill set.
* Reduce the impact of third-party code
  * This recommended that the third-party scripts that are delivered through the CDN's be loaded either using async or defer. As the scripts that are used should not be classed as third-party due to them being essential content for the website this cannot be done at this time.
* Image elements do not have explicit width and height
  * This is the same as the "Properly size images" in the opportunities, so again I have decided that this is not currently something that I can implement and it will be revisited at a later date.
* Minimize main-thread work
  * This is in relation to the JS files that are linked with the project, unfortunately at this time I have not developed any JS files and this is only in relation to the frameworks that I have loaded, which cannot be changed by myself.

### **Desktop**
Initial score 99/100

#### **Lab Data**
* First Contentful Paint - 0.7s (good)
* Time to Interactive - 0.8s (good)
* Speed Index - 0.7s (good)
* Total Blocking Time - 0ms (good)
* Largest Contentful Paint - 0.8s (good)
* Cumulative Layout Shift 0.001 (good)

**Opportunities Identified**
* Properly size images - Estimated saving 9.02s
  * As with the testing in the mobile section, I tried to follow the suggestions and the documentation that was provided but at this time I was unable to resolve the issue.
* Eliminate render-blocking resources - Estimated saving 0.49s
  * This is also the same as the issue with the mobile section so cannot be resolved as the scripts identified are needed for the site.

**Diagnostics**
* Avoid enormous network payloads
  * Lazyload was added to the webpage to reduce the amount of data required when loading images.
* Serve static assets with an efficient cache policy
  * This recommended that the cache-control be increased to speed up multiple visits. After researching into this I found [this article](https://webapps.stackexchange.com/questions/119286/caching-assets-in-website-served-from-github-pages) which shows that due to the deployment on GitHub Pages it is not possible to increase this. I am unable to resolve this with the current resources and skill set.
* Image elements do not have explicit width and height
  * This is the same as the "Properly size images" in the opportunities, so again I have decided that this is not currently something that I can implement and it will be revisited at a later date.

---

**Browser testing**
I tested the index page across FireFox, Brave, Google Chrome, Edge, Opera, and vivaldi that are all installed on my computer and then Safari from my iPhone. 

After the adjustments that were already made for the index page no issue were identified from looking at it with multiple browsers.

[Back to index](#contents)

---

## **Information.html**
Initial check for errors in code done using [W3C Markup Validation Service](https://validator.w3.org/) - No issues or warnings were shown from this.

The page was then checked for spelling mistakes using [typosaurus](https://typosaur.us/) - 3 errors were identified that were then amended.

---

I then moved on to test with [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/) this came back with the following audit points that needed to be addressed.

### **Mobile**
Initial score 69/100

#### **Lab Data**
* First Contentful Paint - 3.1s (high)
* Time to Interactive - 3.1s (good)
* Speed Index - 3.1s (good)
* Total Blocking Time - 0ms (good)
* Largest Contentful Paint - 10.2s (high)
* Cumulative Layout Shift 0 (good)

**Opportunities Identified**
* Properly size images - Estimated saving 7.32s
  * This recommended that I use multiple images to save load times on images. I tested this by using the [ImageMagick CLI](https://www.imagemagick.org/script/index.php) to resize and then using `srcset` property on the images but I was unable to get this to properly function and due to time restrictions on the project I had decided to leave this to be revisited in future to implement.
* Eliminate render-blocking resources - Estimated saving 1.12s
  * This was showing that the bootstrap and FA CDN scripts should be loaded with async or defer but due to the importance of the two and errors caused by using these with either of the two I am unable to resolve this issue.
* Remove unused CSS - estimated saving 0.31s
  * This was showing that the CSS files from bootstrap and FontAwesome were not used, but the classes and styling from both of these are used consistently throughout this page so they cannot be removed.

**Diagnostics**
* Reduce the impact of third-party code
  * This recommended that the third-party scripts that are delivered through the CDN's be loaded either using async or defer. As the scripts that are used should not be classed as third-party due to them being essential content for the website this cannot be done at this time.
* Image elements do not have explicit width and height
  * This is the same as the "Properly size images" in the opportunities, so again I have decided that this is not currently something that I can implement and it will be revisited at a later date.
* Serve static assets with an efficient cache policy
  * This recommended that the cache-control be increased to speed up multiple visits. After researching into this I found [this article](https://webapps.stackexchange.com/questions/119286/caching-assets-in-website-served-from-github-pages) which shows that due to the deployment on GitHub Pages it is not possible to increase this. I am unable to resolve this with the current resources and skill set.

### **Desktop**
Initial score 99/100

#### **Lab Data**
* First Contentful Paint - 0.8s (good)
* Time to Interactive - 0.8s (good)
* Speed Index - 0.8s (good)
* Total Blocking Time - 0ms (good)
* Largest Contentful Paint - 0.8s (good)
* Cumulative Layout Shift 0.011 (good)

**Opportunities Identified**
* Properly size images - Estimated saving 1.1s
  * As with the testing in the mobile section, I tried to follow the suggestions and the documentation that was provided but at this time I was unable to resolve the issue.
* Eliminate render-blocking resources - Estimated saving 0.53s
  * This is also the same as the issue with the mobile section so cannot be resolved as the scripts identified are needed for the site.

**Diagnostics**
* Image elements do not have explicit width and height
  * This is the same as the "Properly size images" in the opportunities, so again I have decided that this is not currently something that I can implement and it will be revisited at a later date.
* Serve static assets with an efficient cache policy
  * This recommended that the cache-control be increased to speed up multiple visits. After researching into this I found [this article](https://webapps.stackexchange.com/questions/119286/caching-assets-in-website-served-from-github-pages) which shows that due to the deployment on GitHub Pages it is not possible to increase this. I am unable to resolve this with the current resources and skill set.

---

**Browser testing**
I tested the index page across FireFox, Brave, Google Chrome, Edge, Opera, and vivaldi that are all installed on my computer and then Safari from my iPhone. 

After the adjustments that were already made for the index page no issue were identified from looking at it with multiple browsers.

[Back to index](#contents)

--- 

## **Pricing.html**
Initial check for errors in code done using [W3C Markup Validation Service](https://validator.w3.org/) - No issues were identified with this test.

The page was then checked for spelling mistakes using [typosaurus](https://typosaur.us/) - 3 errors were identified using this that were then corrected to the correct context/spellings.

---

I then moved on to test with [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/) this came back with the following audit points that needed to be addressed.

### **Mobile**
Initial score 67/100

#### **Lab Data**
* First Contentful Paint - 3.4s (high)
* Time to Interactive - 3.4s (good)
* Speed Index - 3.4s (good)
* Total Blocking Time - 0ms (good)
* Largest Contentful Paint - 10.7s (high)
* Cumulative Layout Shift 0.002 (good)

**Opportunities Identified**
* Properly size images - Estimated saving 16.47s
  * This recommended that I use multiple images to save load times on images. I tested this by using the [ImageMagick CLI](https://www.imagemagick.org/script/index.php) to resize and then using `srcset` property on the images but I was unable to get this to properly function and due to time restrictions on the project I had decided to leave this to be revisited in future to implement.
* Eliminate render-blocking resources - Estimated saving 1.42s
  * This was showing that the bootstrap and FA CDN scripts should be loaded with async or defer but due to the importance of the two and errors caused by using these with either of the two I am unable to resolve this issue.

**Diagnostics**
* Serve static assets with an efficient cache policy
  * This recommended that the cache-control be increased to speed up multiple visits. After researching into this I found [this article](https://webapps.stackexchange.com/questions/119286/caching-assets-in-website-served-from-github-pages) which shows that due to the deployment on GitHub Pages it is not possible to increase this. I am unable to resolve this with the current resources and skill set.
* Reduce the impact of third-party code
  * This recommended that the third-party scripts that are delivered through the CDN's be loaded either using async or defer. As the scripts that are used should not be classed as third-party due to them being essential content for the website this cannot be done at this time.
* Image elements do not have explicit width and height
  * This is the same as the "Properly size images" in the opportunities, so again I have decided that this is not currently something that I can implement and it will be revisited at a later date.
* Avoid enormous network payloads
  * Lazyload was added to the webpage to reduce the amount of data required when loading images.
* Minimize main-thread work
  * This is in relation to the JS files that are linked with the project, unfortunately at this time I have not developed any JS files and this is only in relation to the frameworks that I have loaded, which cannot be changed by myself.

### **Desktop**
Initial score 79/100

#### **Lab Data**
* First Contentful Paint - 0.8s (good)
* Time to Interactive - 1.2s (good)
* Speed Index - 0.9s (good)
* Total Blocking Time - 290ms (high)
* Largest Contentful Paint - 2.0s (high)
* Cumulative Layout Shift 0.011 (good)

**Opportunities Identified**
* Properly size images - Estimated saving 2.54s
  * This recommended that I use multiple images to save load times on images. I tested this by using the [ImageMagick CLI](https://www.imagemagick.org/script/index.php) to resize and then using `srcset` property on the images but I was unable to get this to properly function and due to time restrictions on the project I had decided to leave this to be revisited in future to implement.
* Eliminate render-blocking resources - Estimated saving 0.54s
  * This is also the same as the issue with the mobile section so cannot be resolved as the scripts identified are needed for the site.

**Diagnostics**
* Serve static assets with an efficient cache policy
  * This recommended that the cache-control be increased to speed up multiple visits. After researching into this I found [this article](https://webapps.stackexchange.com/questions/119286/caching-assets-in-website-served-from-github-pages) which shows that due to the deployment on GitHub Pages it is not possible to increase this. I am unable to resolve this with the current resources and skill set.
* Reduce the impact of third-party code
  * This recommended that the third-party scripts that are delivered through the CDN's be loaded either using async or defer. As the scripts that are used should not be classed as third-party due to them being essential content for the website this cannot be done at this time.
* Image elements do not have explicit width and height
  * This is the same as the "Properly size images" in the opportunities, so again I have decided that this is not currently something that I can implement and it will be revisited at a later date.
* Avoid enormous network payloads
  * Lazyload was added to the webpage to reduce the amount of data required when loading images.

---

**Browser testing**
I tested the index page across FireFox, Brave, Google Chrome, Edge, Opera, and vivaldi that are all installed on my computer and then Safari from my iPhone. 

After the adjustments that were already made for the index page no issue were identified from looking at it with multiple browsers.

[Back to index](#contents)

---

## **404.html**
Initial check for errors in code done using [W3C Markup Validation Service](https://validator.w3.org/)

* `<a>` must not appear as a descendant of the `button` element
  * This error was resolved by moving the `<a>` outside of the button element, everything still functioned the same, but it would now pass validation.

The page was then checked for spelling mistakes using [typosaurus](https://typosaur.us/)

---

I then moved on to test with [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/) this came back with the following audit points that needed to be addressed.

### **Mobile**
Initial score 69/100

#### **Lab Data**
* First Contentful Paint - 3.1s (high)
* Time to Interactive - 3.1s (good)
* Speed Index - 3.2s (good)
* Total Blocking Time - 0ms (good)
* Largest Contentful Paint - 17.9s (high)
* Cumulative Layout Shift 0 (good)

**Opportunities Identified**
* Eliminate render-blocking resources - Estimated saving 1.12s
  * This was showing that the bootstrap and FA CDN scripts should be loaded with async or defer but due to the importance of the two and errors caused by using these with either of the two I am unable to resolve this issue.
* Remove unused CSS - estimated saving 0.3s
  * This was showing that the CSS files from bootstrap and FontAwesome were not used, but the classes and styling from both of these are used consistently throughout this page so they cannot be removed.
* Properly size images - Estimated saving 0.15s
  * This recommended that I use multiple images to save load times on images. I tested this by using the [ImageMagick CLI](https://www.imagemagick.org/script/index.php) to resize and then using `srcset` property on the images but I was unable to get this to properly function and due to time restrictions on the project I had decided to leave this to be revisited in future to implement.

**Diagnostics**
* Serve static assets with an efficient cache policy
  * This recommended that the cache-control be increased to speed up multiple visits. After researching into this I found [this article](https://webapps.stackexchange.com/questions/119286/caching-assets-in-website-served-from-github-pages) which shows that due to the deployment on GitHub Pages it is not possible to increase this. I am unable to resolve this with the current resources and skill set.
* Avoid enormous network payloads
  * Lazyload was added to the webpage to reduce the amount of data required when loading images.

### **Desktop**
Initial score 82/100

#### **Lab Data**
* First Contentful Paint - 0.7s (good)
* Time to Interactive - 0.7s (good)
* Speed Index - 1.2s (good)
* Total Blocking Time - 0ms (good)
* Largest Contentful Paint - 3.1s (high)
* Cumulative Layout Shift 0.001 (good)

**Opportunities Identified**
* Eliminate render-blocking resources - Estimated saving 0.49s
  * This is also the same as the issue with the mobile section so cannot be resolved as the scripts identified are needed for the site.

**Diagnostics**
* Serve static assets with an efficient cache policy
  * This recommended that the cache-control be increased to speed up multiple visits. After researching into this I found [this article](https://webapps.stackexchange.com/questions/119286/caching-assets-in-website-served-from-github-pages) which shows that due to the deployment on GitHub Pages it is not possible to increase this. I am unable to resolve this with the current resources and skill set.
* Avoid enormous network payloads
  * Lazyload was added to the webpage to reduce the amount of data required when loading images.

---

**Browser testing**
I tested the index page across FireFox, Brave, Google Chrome, Edge, Opera, and vivaldi that are all installed on my computer and then Safari from my iPhone. 

After the adjustments that were already made for the index page no issue were identified from looking at it with multiple browsers.

[Back to index](#contents)

---

# **CSS**
## **Style.css**

Initially this file was checked with [W3C CSS Validation Service Jigsaw](https://jigsaw.w3.org/css-validator/)

The document passed validation as CSS level 3 + SVG, however it did produce the following 3 warnings:

* `-webkit-background-size` is an unknown vendor extension.
* `-moz-background-size` is an unknown vendor extension.
* `-o-background-size` is an unknown vendor extension.

I felt that these 3 warnings were not cause for concern, all of the unknown vendor extension warnings are because it can only validate against valid code, which the vendor extensions are proprietary code but are needed for browser compatibility. These codes will always show as invalid because of this. [Article response by RyanReese explaining this.](https://www.sitepoint.com/community/t/css-validation-unknown-vendor-extensions/125616)

When further checking the styling on each page was correct, I had noticed that the classes and styling that was used only accommodated for 576px and upwards (as this is the sm breakpoint with bootstrap). However when testing this with my iPhone, I noticed that the styling was not correct and the layout drastically changed from what it should have been. To rectify this, I have gone back through the CSS styling and amended what was incorrect and added new media queries to accommodate what the original styling had looked like on the larger sizes as this website has been developed with a mobile first design.

## **Utilities.css**