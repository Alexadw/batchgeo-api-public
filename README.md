#BatchGeo API - Public Alpha

##Welcome

This is the public alpha version of the BatchGeo JS & HTML API. The BatchGeo API's allow for easy batch geocoding. We let you provide addresses just like you would in Google Maps. No complicated lats and longs. We also allow you to pick what flavor of API you want. If your site is static such as a blog, brochure site, etc then the HTML API is probably for you. If you have a dynamic site or app the JS API is going to be your best bet. Oh, and did we mention you can even make money of your maps?

## Batch Geocoding? When Would I Need That?

More than you probably think. Here are some everyday examples:

###Blogger
You have a blog post about all the 10 best restaurants in downtown Portland, OR. How would you plot those 10? With BatchGeo's HTML API you could just make a list of addresses in your normal WYSIWYG editor and give it a special class and voila! You have a map with 10 markers!

###Freelance Web Designer
You are building a site for a realtor and he wants to provide all of his listings. You could just let him list out the addresses in a WYSIWYG editor and it'll plot it for him.

###App Developer
You're building some app that requires a map with more than just one marker. You could learn the entire Google Maps API, geocode all the requests, and cache them all, or you could just use our JS API.

## OK, so what's the catch?

The API is totally free of charge. There _is_ an ad on the right side of the map, but this is [required by Google](http://googlegeodevelopers.blogspot.com/2011/04/updates-to-google-maps-apigoogle-earth.html), not by us. Google lets you place your own ads in place of theirs though. If you want to do this we're adding an option to put your AdSense ID in there in place of theirs. This is in the very near future. It'll be an option in the `options()` method or as a data attribute for the HTML API like `data-batchgeo-adsense`.

## Sounds good, how do I get started?

There are two paths you can go as we said above. There is the HTML API for static sites and the JS API for more dynamic sites. There are tutorials for each. Above in the GitHub repo click on the folder you want and it should have at least one tutorial for you. More will come.

## Uh oh... I think I broke something

No problem, we want you to break it. If you find a bug or there is something missing let us know in the Issue Tracker above.