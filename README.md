# HouseHunting
Some tools and tricks I used while house hunting. One is to get transaction prices for free and one is to get full floorplans with square meters per room etc. The final one is a about getting pictures of old houses.

**Get Floorplan**
Go to an available property on funda.nl which has floorplans. Open the floorplan, the url in your taskbar should look something like this: https://www.funda.nl/detail/koop/amsterdam/huis-keizersgracht-657/43797480/media/plattegrond/1/ Now press F12 on your keyboard, this should open devtools on chrome/edge/firefox. Now go the tab 'Network' and press F5 to refresh the page. You should now under 'Name' see a url like this: https://fmlpub.s3-eu-west-1.amazonaws.com/164881613.fml?editor_version=2.31.5&auth_token=undefined Open this url in a new page. Now press ctrl+s to save the page. It will try to save it as a .json file. Change it to: Save as type 'all files (*.*) Rename the file to have the extension '.fml' (e.g. floorplan.fml) Now go to https://floorplanner.com/ and create a free account. Now create a new project, you will see a blue button with 'Import FML'. Import the file you just saved and voila the entire house is available including square meters per room, wall etc.

**Get transaction prices**
--EDIT 03-2025 -- Walter Living has introduced a subscription model. This data is no longer available for free--
This one is quite simple. Make an account on https://walterliving.com/. When logged in create a free report for the property you are interested in. Under the block with 'how can we help' there should be an option to view the Walter report. This will give you an calculated valuation per maintenance state. This is nice on it's own but there is more! Under 'Walter desktoptaxatie' click 'woningwaarde berekenen'. It will start looking for properties close by. On the next page you will see 'Bekijk woningen in de buurt' on the very right of that text you'll see an Excel Icon. Click that and you will get an excel with data on the properties in the neighborhood. It does not state the transaction price but it does contain the list price and the bidding %. List price * bidding % = Transaction price (with max 0,5% rounding margin). You can zoom in and out of the map to have more or less properties in the download. There is a max in properties that it will download. Want more? Find a similar property just outside the range and create a report for that property. This will contain new properties further away. Houses must've been sold definitively and registered at Kadaster before bidding % is available.

**Get property pictures**
This python notebook will allow you to find pictures of properties that have been listed before but are not listed on Funda anymore or just to scrape pictures of houses that are currently being offered. You can find pictures of the last time it was listed if you are quick or similar houses in the neighbourhood listed over a year ago.

**For old homes there are two options**

**Option 1:** try to find the address on https://www.miljoenhuizen.nl/ and open the thumbnail image in a new tab. This should provide you with a funda link to the picture. Paste this link in 'starting_url' to scrape the subsequent pictures. Quite often multiple houses are uploaded at the same time making the pictures not increase sequential. It is not fool proof but in many cases it will provide pictures of the house you are looking for. It can retrieve pictures of listings as far as 15 years ago!

**Option 2:** look if the house has a thumbnail on https://walterliving.com/. The thumbnail is available in multiple pages on some you might need to retrieve the url through 'inspect element' on some you can open the image on a new tab. Paste this link in 'starting_url' to scrape the pictures. It can retrieve pictures of listings as far as +-5 years ago.

When a new house is offered make sure to try this the same day as both options will scrape the new pictures at night and refresh their site with the new pictures thus losing the link to the past in the process.

**Some extra tips that came in to mind.**

https://KadastraleKaart.com If you want to know if the house or the garden will be shaded then lookup the address on this site. Click 'Adres' and then scroll down to 'Zon en schaduw rondom adres'. It will give you an idea of the shade year round.

https://bing.com/maps/ One cool thing that bing maps has to offer is birds eye view. Look up the address and right click. You should see the opion 'View in Birds eye' or 'bekijk in vogelvlucht'. Availability and date of the images varies but for quite a big portion of the Netherlands high-res aerial close up images from all angles are available.

https://3dbag.nl/ Very cool site imo. For every building you can easily find the height of each part of the building and the slope of the roof(s). Also the estimated building and roof sizes are available. Accuracy depends on the straightforwardness of the building geometry.
