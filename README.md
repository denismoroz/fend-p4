## Website Performance Optimization portfolio project


####Part 1: Optimize PageSpeed Insights score for index.html

Optimizations:
 1. Get rid of Google Analitics JS. There are no cridentials for it so why we need to load it at all.
 2. Moved CSS loading to loadCSS to speed it up
 3. Make sure that print css is loaded only for media=print
 4. resize pizzeria.jpg to small size not to load 2.3 mb each time
 5. minimify html and css use html-minifier and clean css for that
 6. use image optim to optimize images

* [Optimized index.html](http://denismoroz.github.io/fend-p4/ "Optimized portfolio")
* [Optimized index.html without minification ](http://denismoroz.github.io/fend-p4/index.full.html "Not minified optimized portfolio")

####Part 2: Optimize Frames per Second in pizza.html

Changes for scrolling:
 Problem function is views/js/main.js updatePositions(). Main issue that it is recalucate phase var for each element.

 1. precalucate phases map, because there are only 5 values for phases. We do % 5 on item number that lead looping of phase from 0 to 4.
 2. use right phase on calculation moving pizzas.

Changes for change pizza size:
 1. Request all .randomPizzaContainer only once
 2. Use % to calculate newWidth and use switch to calculate it only once
