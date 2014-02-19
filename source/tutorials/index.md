---
title: Tutorials

language_tabs:
  - javascript

toc_footers:
 - <a href='/'>Getting Started</a>
 - <a href='/tutorials/'>Tutorials</a>
 - <a href='/reference/'>API Reference</a>
 - <a href='http://www.nutrio.com'>Nutrio</a>
 - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>
---


#Convert decimals to fractions 
```javascript
var toFraction = function (value, accuracy) {
    if (value == 0) {
      return {whole:0, numerator: 0, denominator: 1};
    }
    
    var denominator, error, numerator, whole;
    if (!accuracy) {
        accuracy = .01;
    }
    denominator = 0;
    numerator = null;
    while (!numerator || error > accuracy) {
        denominator++;
        numerator = Math.round(value * denominator);
        var decimal = numerator / denominator;
        error = Math.abs(Math.abs(value) - Math.abs(decimal));
        if (denominator > 20) break;
    }
    var mixed_numerator = numerator;
    numerator = numerator % denominator;
    var whole = (mixed_numerator - numerator) / denominator;
    var fraction = {
        whole: whole,
        numerator: numerator,
        denominator: denominator
    };
    return fraction;
};
````

#Convert minutes to hours 
#Determine when to use the plural version of a name
#Make a string lower-case
#Convert dates to/from YYYYMMDD format
