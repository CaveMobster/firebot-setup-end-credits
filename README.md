# End Credits test v2

by [cavemobster](https://github.com/CaveMobster)

This setup adds end credits to show at the end of the stream.

## What it does

The bot collects the names of all of the below, puts them in files and then updates credits.html, which you can include in a browser source in OBS. When a certain event hasn't happened, for example if you didn't get any tips, it will exclude that block from the credits. The files get cleared every time Firebot starts, but you can also use a command or use your stream deck. See here for detailed instructions.

The default options:

- Mods
- Subs & resubs
- Gift subs (only the names of the gifters will be displayed)
- Bits
- Raids
- Follows

By importing the setup you will include all of them, but you can simply remove the ones you don't want or need after the import. See here for detailed instructions.

## How do I get this to display in OBS?

Since this setup also requires some setting up in OBS, I wrote a detailed instructions below.

[Instructions for V1](https://github.com/ImaginaryResources/firebot-setup-end-credits/tree/master/v1)  
[Instructions for V2](https://github.com/ImaginaryResources/firebot-setup-end-credits/tree/master/v2)

## This Setup Adds:

### Commands

- !rollcredits
- !clearcredits

### Event Sets

- Credits

### Preset Effect List

- [credits] Roll credits
- [credits] Clear credits
- [credits] Write To File

### Variable Macros

- creditsResourcePath
- creditsBlockNames
- creditsTypes

### Quick Action

- Roll Credits
- Clear Credits

## Import Questions

### Create a new folder with an empty credits.html file and enter the path here. Example: C:/Stream/Credits

Default: `blank`

### Title for the mods block

Default: Mods

### Title for the subs & resubs block

Default: Subs & Resubs

### Title for the gift subs block

Default: Gift Subs

### Title for the bits block

Default: Bits

### Title for the raids block

Default: Raids

### Title for the follows block

Default: Follows
