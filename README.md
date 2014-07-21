hyphenator
==========

Hyphenator.js
for more infor please visit: https://code.google.com/p/hyphenator/


example:
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
    
    $(d).ready(function () {
       hyphenator();

        Hyphenator.config({
            displaytogglebox : false,
            minwordlength : 10
        });
        
        Hyphenator.run();
    }
    
}(window, document, jQuery));    
