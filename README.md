# HouseHunting
Some tools and tricks I used while house hunting. Two are about getting pictures of old houses, one is to get transaction prices for free and the last on is to get full floorplans with square meters per room etc.

**Get Floorplan**
Go to an available property on funda.nl which has floorplans. Open the floorplan, the url in your taskbar should look something like this:
https://www.funda.nl/detail/koop/amsterdam/huis-keizersgracht-657/43797480/media/plattegrond/1/
Now press F12 on your keyboard, this should open devtools on chrome/edge/firefox. Now go the tab 'Network' and press F5 to refresh the page. You should now under 'Name' see a url like this:
https://fmlpub.s3-eu-west-1.amazonaws.com/164881613.fml?editor_version=2.31.5&auth_token=undefined
Open this url in a new page. Now press ctrl+s to save the page. It will try to save it as a .json file. Change it to: Save as type 'all files (*.*) Rename the file to have the extension '.fml' 
Now go to https://floorplanner.com/ and create a free account. Now create a new project, you will see a blue button with 'Import FML'. Import the file you just saved and voila the entire house is available including square meters per room, wall etc. 

**Get transaction prices**
This one is quite simple. Make an account on https://walterliving.com/. When logged in create a report for the property you are interested in. Under block with 'how can we help' there should be an option to view the walter report. This will give you an calculated valuation per maintenance state. This is nice on it's own but there is more! Under 'Walter desktoptaxatie' click 'woningwaarde berekenen'. It will start looking for properties close by. On the next page you will see 'Bekijk woningen in de buurt' on the very right of that text you'll see an Excel Icon. Click that and you will get a lot of data on the properties in the neighbourhood. It does not state the transaction price but it does contain the list price and the bidding %. List price * bidding % = transation price (with max 0,5% margin). You can zoom in and out of the map to have more or less properties in the download. There is a max in properties that it will download. Want more? Find a similar property just outside the range and create a report for that property. This will contain new properties further away.

**Get property pictures**
This python notebook will allow you to find pictures of properties that have been listed before but are not listed on Funda anymore or just to scrape pictures of houses that are currently being offered. 

**For old homes there are two options. **
**Option 1:** try to find the address on https://www.miljoenhuizen.nl/ and open the thumbnail image in a new tab. This should provide you with a funda link to the picture. Paste this link in 'starting_url' to scrape the following pictures. Quite often multiple houses are uploaded at the same time making the pictures not increase sequential.
**Option 2:** look if the house has a thumbnail on https://walterliving.com/. The thumbnail is available in multiple pages on some you might need to retrieve the url through 'inspect element' on some you can open the image on a new tab. Paste this link in 'starting_url' to scrape the pictures

When a new house is offered make sure to try this the same day as both options will scrape the new pictures and refresh their site 
with the new pictures and thus losing the link to the past in the process. 

