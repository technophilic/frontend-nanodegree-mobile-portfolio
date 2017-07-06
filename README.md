# Web Performance
Repository containing resources for the Website Optimization project of udacity frontend nanodegree.
### Open index.html to launch the app
### gh-pages hosted live version - [here](https://technophilic.github.io/frontend-nanodegree-mobile-portfolio/)
# Changes made:
### Portfollio :
* Inlined critical rendering styles
* Rest of the styles load asynchronously using [loadCSS](https://github.com/filamentgroup/loadCSS)
* Critical scripts are inlined
* Rest of the scripts load asynchronously
* Minified external css and scripts
* Compressed images
* All assets are hosted at cloudinary since gh-pages doesn't allow us to enable caching.
* Also gzip is enabled on these assets

### Pizzeria :

**60 FPS :**

* Moved the ```#movingPizzas1``` element right below body
* Separated all the moving pizza into one separate layer (this is better than one layer for each pizza as lot of pizzas are present. Compositor will cause a huge frame drop if done this way.)
* Minimized the DOM queries during scroll via memoization
* fetched ```scrollTop``` from the event data passed to the callback function during the scroll event instead of doing ``` document.body.scrollTop ``` every time

**Computational Efficiency :**
* Minimized the DOM queries during scroll via memoization
* Common computations are factored outside the loop to increase runtime efficiency.
* Made sure ```Recalculate Styles``` doesn't happen after ```Layout```