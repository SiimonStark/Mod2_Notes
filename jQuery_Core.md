##Link to Study Guide:
https://learn.jquery.com/using-jquery-core/

##$ vs $()
	•	Methods called on jQuery selections are in the $.fn namespace, and automatically receive and return the selection as this.
	•	Methods in the $ namespace are generally utility-type methods, and do not work with selections; they are not automatically passed any arguments, and their return value will vary.
–	Object methods tend to be .each()
–	While utility methods will look like $.each()
–	Which is a method that isn’t called on a selection

##$(document).ready()
–	Code included in $( document ).ready() will only run once the page DOM is ready.
–	You can use a named function in place of the anonymous function
–	Code included in $( window ).on( “load”,  function() {…}) will only run once the entire page including images has loaded.
–	The shorthand is $(function() {…}) , it’s not recommended to use this form as a beginner!

##Avoiding Conflicts with Other Libraries

--Putting jQuery in No-Conflict Mode--
When you put jQuery into no-conflict mode, you have the option of assigning a new variable name to replace the $ alias.
<!-- Putting jQuery into no-conflict mode. -->
var $j = jQuery.noConflict();
// $j is now an alias to the jQuery function; creating the new alias is optional.
 
$j(document).ready(function() {
    $j( "div" ).hid
});/ 
OR, this preferred solution ⤵️ Which passes the $ as an argument.
jQuery.noConflict();
jQuery( document ).ready(function( $ ) {
    // You can use the locally-scoped $ in here as an alias to jQuery.
    $( "div" ).hide();
});

--Including jQuery Before Other Libraries--
If you run your jQuery file before other libraries you don’t have to use the above methods, rather you can use:
// Use full jQuery function name to reference jQuery.
jQuery( document ).ready(function() {
    jQuery( "div" ).hide();
});

##Attributes
The .attr() method acts as both a getter and a setter.
–	As a Setter: it can accept either a key & a value pair or an Object w/ 1 or more pairs.
$( "a" ).attr( "href", "allMyHrefsAreTheSameNow.html" );
$( "a" ).attr({
    title: "all titles are the same too!",
    href: "somethingNew.html"
});
–	As a Getter: it returns the value for the first element.
$( "a" ).attr( "href" ); 
// Returns the href for the first a element in the document

