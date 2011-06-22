#HTML API Tutorial - The Basics

You can view a this demo map in the `tutorial-01.html` file.

**NOTE: You have to run these demos via http(s), not locally (file:///). Also, make sure you always set a height to your maps! If not you'll get a console log saying no height was set and the map won't be visible (because the height is 0px).**

**NOTE ON LARGE DATASETS: If you are playing with this and load 10+ markers you might see a noticeable delay while we geocode it. Don't fret. Once it's loaded it'll be cached on our servers so you, and anyone else viewing the map will see it instantly.**

##Step 1: Load the API
Add the following to the end of the `</body>` (or the `<head>` if you need to).

     <script src="http://api.batchgeo.com/js"></script>


##Step 2: Create a map container

This can be any HTML tag. You'll most likely want to put it in a `<div>`. The only special thing you need to do to your HTML is add a special ID that starts with `batchgeo-map-`. This will tell the API "hey, put a map here". After that second dash you can name it whatever you want. In the example `.html` file it's just name `1`.

Example:

    <div id="batchgeo-map-1"></div>
    
##Step 3: Create a list of addresses

This is simply a `<ul>` or `<ol>` with `<li>`s containing `<address>`es. Each `<li>` is a marker and the `<address>` inside is what will be used as the address. Any additional HTML will be used as the content inside of the popup bubble that appears when you click on a marker.

In the `<ul>` or `<ol>` add an ID with `batchgeo-data-` and after the second dash add the name you gave it in step 2. I named it `1`, so my ID would be: `batchgeo-data-1`.

Example:

    <ul id="batchgeo-data-1">
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
    
###That's it!

If you are having issues, some common pitfalls are:

- Not setting a height to your map. You can do this with just CSS.
- Not matching the names of the IDs of the `batchgeo-data-` and `batchgeo-map-` elements.
- Running this locally. You need to run this on a server (MAMP, WAMP, etc will also work)
