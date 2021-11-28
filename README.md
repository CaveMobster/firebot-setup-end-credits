# End credits

This setup adds end credits to show at the end of the stream.

## What it does
The bot collects the names of all of the below, puts them in files and then updates the html file you created, which you can include in a browser source in OBS. When a certain event hasn't happened, for example if you didn't get any tips, it will exclude that block from the credits. The files get cleared every time Firebot starts, but you can also use a command or use your stream deck.
- Mods
- Follows
- Subs & resubs
- Gift subs (only the names of the gifters will be displayed)
- Bits
- Hosts & raids

## How to download
Right click on [this link](https://github.com/CaveMobster/firebot-setups/blob/master/Credits/credits.firebotsetup?raw=true) and choose "Save Link As...".

## Setup walkthrough
This setup is a bit more complex than others in this repository, because it's includes modifications in OBS.
**Note:** I made this walkthrough using OBS. I can imagine SLOBS is pretty similar, but if you're struggling to make it work, feel free to ask in the #setups channel in the CrowbarTools Discord.

### Import the setup in Firebot
In Firebot:
1. Go to Settings -> Setups
2. Choose Import Setup
3.  Locate the setup file that you downloaded from this page

You will see a bunch of commands, events and preset effect lists that will get added to the bot. Below that, you will find a list of questions, in which you have to provide the path to the folder in which you created the empty `credits.html` file and optionally different names you want to give to, for example, subs.

**Warning**: If you move the files to another place on your computer _after_ the setup, Firebot will no longer know where it's located. If you know where to change all the paths in the events and lists in Firebot, make sure to do that. If you don't, you may want to import the setup again.

### Make the credits show up in OBS
Go to the scene where you want the credits to show up and do the following:
1. Add a new browser source
2. Check the 'Local file' checkbox
3. Click 'Browse' and locate the `credits.html` file
4. Choose the height and width of the browser source (important because the positioning of the credits is based off of these dimensions)
5. Check the 'Refresh browser when scene becomes active' checkbox
6. In the custom CSS, add the following:
```css
body {
	background-color: rgba(0, 0, 0, 0);
	margin: 0px auto;
	color: #FFF;  /* The color of the font, change this to your preferred text color. */
	font-family: Kalam; /* Change this to your preferred font. */
	text-align: center;
	overflow: hidden;
}

.marquee {
	overflow: hidden;
	height: 100%;
}

.marquee-container {
	animation: marquee 45s linear infinite; /* Increase or decrease the 45s value to set how fast the text needs to scroll. */
	height: auto;
}

@keyframes marquee {
	0% { margin-top: 100vh }
	100% { transform: translateY(-100%) }
}

h1 {
/*
	font-size: Title font size, increase or decrease the number to your liking.
	font-weight: Options: 100, 200, 300, 400, 500, 600, 700, 800, 900.
	margin: Increase or decrease the 5px value, this takes care of the space between the title and the names.
*/
	font-size: 35px;
	font-weight: 700;
	margin: 0 0 5px 0;
}

p {
/*
	font-size: Font size of the names, increase or decrease the number to your liking.
	font-weight: Options: 100, 200, 300, 400, 500, 600, 700, 800, 900.
	margin: Increase or decrease the 40px value, this takes care of the space between the blocks.
*/
	font-size: 25px;
	font-weight: 300;
	margin: 0 0 40px 0;
	white-space: pre-line;
}
```

## How to run the credits
There are two ways to run the credits, either by using the command or by using a stream deck.

### With the command:
1. Type !rollcredits in chat
2. Refresh the cache of the browser by either:
    1. Selecting the browser source and clicking 'Refresh' in the bar below the scene preview
    2. Hiding and then showing the browser source by click the eye next to the source twice

### With an Elgato Stream Deck:
1. Go to Effects
2. Click Preset Effect Lists
3. Click the three dots behind `[credits] Roll credits` and choose Edit
4. Click 'How to trigger from StreamDeck' and follow the instructions

I recommend making a multi action button in which you switch to the scene on which the credits are displayed, because you won't have to manually refresh the browser source.


## FAQ

### How do I remove the parts I don't need?
If you don't want to display certain parts of the credits, for example, you don't want the followers to show up, there are two ways to disable them.
1. Disable the event. Go to Events and click on the three dots behind the event you don't want to show up, for example `[credits] Follows`, and choose 'Toggle Enabled'.
2. You remove the event entirely by doing the above, but instead of choosing 'Toggle Enabled', you choose 'Delete'.

### How do I clear the credits?
The credits get cleared every time your bot restarts, but you can also do it manually if needed.
- If you don't have a stream deck, use the `!clearcredits` command.
- If you have an Elgato Stream Deck, go Effects -> Preset Effect Lists. Click on the three dots behind `[credits] Clear credits` and choose Edit. Click on How to trigger from Stream Deck and follow the instructions.

**Warning:** By doing this you remove all of the information the bot collected over the course of the stream, and that is currently irreversable. I'm working on a way to back it up, but be careful with this function for now.

### Can I add other fun things to display in the credits?

Yes! If you know your way around Firebot I suggest you play around with it and see what you can do, but I plan on making extensions of this credits function in the future.

