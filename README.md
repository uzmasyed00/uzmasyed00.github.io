## Website Performance Optimization portfolio project

In order to evaluate performance of index.html, do the following:

1. Host the website on github.io
 - In Github, create a new repository
 - Name your repository username.github.io, replacing username with your GitHub username. Be sure it is public and go ahead and tell GitHub to create a README file upon generating the repo.
 - Clone the above repository locally
 - Place the provided code into the above local repository
 - Push the changes to the server
 - In a browser, navigate to https://username.github.io/index.html to ensure website has been hosted successfully

2. In a browser, navigate to https://developers.google.com/speed/pagespeed/insights/
  - Enter https://username.github.io/index.html in textbox with in-place text "Enter a web url" and hit analyze. This will reveal performance
  of the page on both desktop and mobile

Now, In order to optimize index.html to achieve a target score of at least 90, try the following:

1. Add async tag to the following to load javascript asynchronously
<script src="https://www.google-analytics.com/analytics.js" async></script>

2. Inline css so that the browser did not have to fetch the css file externally

3. Resize and compress pizzeria.jpg

4. Prevent downloading of images from the web. Instead, download it and saved it in the views/images folder and reference them. You can call the images as follows:
- FirstExternalImage
- SecondExternalImage
- ThirdExternalImage

5. Add print and handhelp attribute to fetch css for print and mobile. Also move relevant css for print and mobile into separate files such as print.css and smartphone.css
so that rendering is not blocked if not required

In order to achieve fps of 60 and pizza resize time < 5ms for pizza.html, make the following changes to views/main.js

1. Line 451 - Stored document.querySelectorAll(".randomPizzaContainer") in a variable outside of the for loop as this value was required only once. Reused the variable inside the loop.
2. Line 454 - Since width of each pizza is same, moved calculation of new width outside of the for loop and reused the new width value inside the loop
3. Line 508 - Uses ElementByClassName query instead of document.querySelectorAll for increased performance
4. Line 510 - Cached document.body.scrollTop into a variable so that it does not have to be calculated multiple times in the loop
5. Line 537 - Made change to run the loop only through required number of pizzas visible within a certain screen

Each time you make a change, analyze the page again on PageSpeed Insights to evaluate the performance of index.html and use developer tools to view performace of pizza.html



