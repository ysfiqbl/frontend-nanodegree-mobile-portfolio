## Website Performance Optimization portfolio project

You see a live version of the site [here](http://ysfiqbl.github.io/frontend-nanodegree-mobile-portfolio/)
[Here's](http://ysfiqbl.github.io/frontend-nanodegree-mobile-portfolio/views/pizza.html) a direct link to the pizza.html page
You can also download and extract the zip file and open the index.html and views/pizza.html files in your favorite javascript enabled browser.

To see the PageSpeed score [click here](https://developers.google.com/speed/pagespeed/insights/?url=http%3A%2F%2Fysfiqbl.github.io%2Ffrontend-nanodegree-mobile-portfolio%2F)

###Optimizations to index.html
1. Added async attribute to relevant js scripts.
2. Defined width and height attributes for all images.
3. Compressed images.
4. Inlined CSS.
5. Loaded Google Fonts via JS instead of HTML link tag.

###Optimizations to views/main.js
##Reducing Resize Pizza functionality to less than 5ms.
1. Caching the pizza container divs and the total number of these divs. This was done by moving the call to `document.querySelectorAll(".randomPizzaContainer");` out of the `for` loop, therefore the DOM tree was traversed once an not for each iteration of the for loop.
2. Caching the new width of the pizza container divs. All the `.randomPizzaContainer` elements have the same layout width, this width is `33.33%` and is defined in the `pizzaElementGenerator` function. Therefore the new layout width for all the elements will also be the same. Hence the call to the `determineDx` function can also be moved out the `for` loop.

##Obtained framerate of 60fps