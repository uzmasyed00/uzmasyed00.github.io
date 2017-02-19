## Website Performance Optimization portfolio project

Optimizations made for index.html to receive score of at least 90:

1. Added async tag to the following to load javascript asynchronously
<script src="https://www.google-analytics.com/analytics.js" async></script>

2. Inlined css so that the browser did not have to fetch the css file externally

3. Resized and compressed pizzeria.jpg

4. Prevented downloading of images from the web. Instead, downloaded it and saved it in the views/images folder and referenced them. The images are called:
- FirstExternalImage
- SecondExternalImage
- ThirdExternalImage

5. Added print and handhelp attribute to fetch css for print and mobile. Also moved relevant css for print and mobile into print.css and smartphone.css
so that rendering is not blocked if not required

Optimizations made in main.js to achieve fps of 60 and pizza resize time <5ms:

1. Line 451 - Stored document.querySelectorAll(".randomPizzaContainer") in a variable outside of the forloop as this value was required only once. Reused the variable inside the loop.
2. Line 454 - Since width of each pizza is same, moved calculation of new width outside of the for loop and reused the new width value inside the loop
3. Line 508 - Uses ElementByClassName query instead of document.querySelectorAll for increased performance
4. Line 510 - Cached document.body.scrollTop into a variable so that it does not have to be calculated multiple times in the loop
5. Line 537 - Made change to run the loop only through required number of pizzas visible within a certain screen



