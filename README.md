hyphenator
==========

Hyphenator.js
for more infor please visit: https://code.google.com/p/hyphenator/


example:
```
(function(w, d, $) {

    /**
     * Apply hyphenator Plugin to title
     * @type {Function}
     * @property hyphenator
     * @private
     */
   hyphenator = function () {
        var stStart = "<span class='hyphenate'>",
            stEnd = "</span>",
            elementToHyphenate = $('.title');

        $.each(elementToHyphenate, function (k, v) {
            var elementToHyphenateText = $(v).html();
            $(v).html(stStart + elementToHyphenateText + stEnd);
        });

        return false;
    };
    
    
    /**
     * Call Functions on DomReady
     */
    $(d).ready(function () {
        // Set up elements with 'hyphenate' class
        hyphenator();

        // Config Hyphenator
        // see following for more config properties:
        // https://code.google.com/p/hyphenator/wiki/en_PublicAPI
        Hyphenator.config({
            displaytogglebox : false,
            minwordlength : 10
        });
       
        // Run Hyphenator
        Hyphenator.run();
    }
    
}(window, document, jQuery));    
```
