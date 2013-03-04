#jQuery Scroll Follow

Feedback is welcome and appreciated: http://getsatisfaction.com/netperspective/products/netperspective_jquery_scroll_follow

## OVERVIEW
Scroll Follow is a simple jQuery plugin that enables a DOM object to follow the page as the user scrolls. Scroll Follow has been successfully tested on IE6, IE7, FF2, FF3, Safari 3, and Opera 9 on Windows. It has been successfully tested on FF3 and Safari 3 on MacOSX.

## REQUIREMENTS
[jQuery](http://jquery.com/) (tested with 1.9.1)  
[jQuery UI Core](http://jqueryui.com/) (tested with 1.10.1)  

## OPTIONAL
[jQuery Easing Plugin](http://gsgd.co.uk/sandbox/jquery/easing/)  
[jQuery Cookie Plugin](http://web.archive.org/web/20100721181236/http://www.stilbuero.de/2006/09/17/cookie-plugin-for-jquery/)

## INSTALLATION
Include jQuery:
```javascript
<script type="text/javascript" src="jquery.js"></script>
```
Include required plugins, including Scroll Follow:
```javascript
<script type="text/javascript" src="ui.core.js"></script>
<script type="text/javascript" src="jquery.scrollFollow.js"></script>
```
Call Scroll Follow on the desired DOM object: 
View Example
```javascript
<script type="text/javascript">
  $( '#example' ).scrollFollow();
</script>
```
Or call Scroll Follow on the desired DOM object and give it some parameters: 
View Example
```javascript
<script type="text/javascript">
 $( document ).ready( function () {
   $( '#example' ).scrollFollow( {
    speed: 1000,
    offset: 60,
    killSwitch: 'exampleLink',
    onText: 'Disable Follow',
    offText: 'Enable Follow'
   } );
 } );
</script>
```
The Scroll Follow object will remain inside its immediate container. 
View Example
Or you can specify a parent (by ID) for the Scroll Follow object to consider its container: 
View Example
```javascript
<script type="text/javascript">
 $( document ).ready( function () {
  $( '#example' ).scrollFollow( {
   container: 'outer'
  } );
 } );
</script>
```
Scroll Follow uses the "top" property of an object to slide it. Therefore, the "position" of the object must be set to either "relative" or "absolute." Other than that limitation, the Scroll Follow object should be completely configured through CSS.

## PARAMETERS
* speed  
  *int - default: 500*  
  The duration of the sliding animation (in milliseconds). The smaller the value, the faster the animation.
* easing  
  *string - default: 'linear'*  
  If included, use any one of the easing options from the easing plugin. Uses 'linear' by default which provides no easing.
* offset  
  *int - default: 0*  
  Number of pixels the Scroll Follow object should remain from top of viewport.
* container  
  *string - default: object's immediate parent*  
  ID of the containing div.
* killSwitch  
  *string - default: 'killSwitch'*  
  ID of the On/Off toggle element. Requires the jQuery Cookie plugin.
* onText  
  *string - default: 'Turn Slide Off'*  
  killSwitch text to be displayed if sliding is enabled.
* offText  
  *string - default: 'Turn Slide On'*  
  killSwitch text to be displayed if sliding is disabled.
* relativeTo  
  *string - default: 'top'*  
  Scroll animation can be relative to either the 'top' or 'bottom' of the viewport.
* delay  
  *int - default: 0*  
  Time between the end of the scroll and the beginning of the animation in milliseconds.

## HISTORY
* March 3, 2013 - Version 0.4.1
  * Fixed jQuery compatibility up to 1.9.1
* October 29, 2008 - Version 0.4.0  
  * Added 'delay' parameter which sets the scroll follow to only happen a set interval after the last scroll  
  * Added a window.resize listener  
  * Removed the requirement for the easing plugin (still necessary for advanced easing settings)  
  * Removed the requirement for the cookie plugin (still necessary for using a killswitch)  
  * Removed 'animate' parameter. Effect can be fully realized with CSS  
  * Fixed typo in version of ui.core.js tested  
* October 22, 2008 - Version 0.3.1  
  * Fixed behavior when 'relativeTo' is set to 'bottom.' Previous behavior allowed the scrolling object to break out of the top of its container.  
* October 7, 2008 - Version 0.3.0  
  * Reworked animating logic to take more situations into account.  
  * Added animating to initial position on page load.  
  * Added animating to initial position on reenabling of following.  
  * Added 'relativeTo' parameter: allows the scroll following object to reposition based on the top or the bottom of the viewport.  
* July 2, 2008 - Version 0.2.1  
  * Minor bug fix.  
* July 2, 2008 - Version 0.2.0  
  * Added 'animate' parameter. Allows a scroll following effect with no animation.  
* May 23, 2008 - Version 0.1.0  
  * Initial Release  
