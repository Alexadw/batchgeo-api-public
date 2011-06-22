#JS API Tutorial - The Basics

You can view a this demo map in the `tutorial-01.html` file.

**NOTE: You have to run these demos via http(s), not locally (file:///). Also, make sure you always set a height to your maps! If not you'll get a console log saying no height was set and the map won't be visible (because the height is 0px).**

**NOTE ON LARGE DATASETS: If you are playing with this and load 10+ markers you might see a noticeable delay while we geocode it. Don't fret. Once it's loaded it'll be cached on our servers so you, and anyone else viewing the map will see it instantly.**

##Step 1: Load the API
Add the following to the end of the `</body>` (or the `<head>` if you need to).

     <script src="http://api.batchgeo.com/js"></script>


##Step 2: The batchgeo.ready() load function
Next, in a new script tag, or in an external script, add:

    batchgeo.ready(function(){
      //We can run batchgeo code in here!
    });
    
On the backend the API is loading a lot of JS from multiple sources so `batchgeo.ready()` waits for everything to be ready and the runs your code that's inside. This is basically the same as jQuery 's `$(document).ready()` (or `$(function(){})` for short) function for those of you who are familiar with it.
    
**NOTE: You can have as many of these as you want, but you only need one.**

##Step 3: Select your empty DOM element

We need a place for your map to be generated. This can be any DOM element you want whether a `<div>`, `<article>`, or a made up one. On the backend we use the [Sizzle](http://sizzlejs.com) selector engine, so basically any CSS selector will work. For example, if you had an element with the id of `#my-map` you'd select it by doing:

    batchgeo('#my-map')


This is like jQuery's `$(#someSelector)`. Anything jQuery supports, we support the same thing as far as CSS selectors.

##Step 4: Give it a source

Now that BatchGeo is loaded you need to give it a source of addresses. It takes JSON, JS objects, or an HTML list element. The JSON and JS objects need two attributes: `address` and `info`. `address` contains the address or location name (like "crystal ballroom, portland, or" or a physical address). The `info` is what shows up in the bubble that pops up when you click on a marker. You can include raw text or HTML, but the `info` parameter is not required.

The HTML list is the same concept, but slightly different. You have a `<ol>` or `<ul>` list you target which has `<li>`s with an `<address>` tag inside for the addresses and then any other content in the `<li>` will be included as the info.

###JS object (and could be JSON):

    var myAddresses = [
      {
        address:"3862 Southeast Hawthorne Boulevard Portland, OR",
        info:"The Hawthorne Theater in SE"
      },
      {
        address:"8 Northwest 6th Avenue Portland, OR",
        info:"The Roseland Theater on Burnside"
      },
      {
        address:"1332 W. Burnside, Portland",
        info:"A <strong style=\"color:red\">very</strong> fun venue, the Crystal Ballroom"
      }
    ];

###HTML

    <ul id="address-list">
      <li>
        <address>3862 Southeast Hawthorne Boulevard Portland, OR</address>
        <p>The Hawthorne Theater in SE</p>
      </li>
      <li>
        <address>8 Northwest 6th Avenue Portland, OR</address>
        <p>The Roseland Theater on Burnside</p>
      </li>
      <li>
        <address>1332 W. Burnside, Portland</address>
        <p>A <strong style="color:red">very</strong> fun venue, the Crystal Ballroom</p>
      </li>
    </ul>
    

We add this onto our existing code from step 3 where we selected the element and we get:

    //For the JS Object example
    batchgeo('#my-map').source(myAddress);
    
    //For the HTML example
    batchgeo('#my-map').source('#address-list');

**NOTE: For HTML sources it will NOT hide the list. The only thing it will do is make the list items clickable and by clicking them it will open up the corresponding marker. You can see a demo of this in the `.html` page.**

##Step 5: Map it!

The last step is simply add .map(). This gives us:

    //For the JS Object example
    batchgeo('#my-map').source(myAddress).map();
    
    //For the HTML example
    batchgeo('#my-map').source('#address-list').map(); 

**NOTE: `.map()` is equal to `.map('create')`. `.map()` is simply the shorthand. To remove the map select the map and do .map('remove');**