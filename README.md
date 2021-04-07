# MAL_CSS
These are my css changes to MAL to be able to share with friends and keep them updated!

I made my changes based on the design from [Valerio_Lydon](https://myanimelist.net/forum/?topicid=1723114), so most of the source code and the installation instructions are actually from his own guide. 


# INSTALLATION

### 1. First you need to chose what to [show on your list](https://myanimelist.net/editprofile.php?go=listpreferences). But keep this in mind: All items work, but there are some situations that can look strange. Here's what to be careful of:
* Groupings (items that should be enabled together):
  * "Chapters" + "Volumes"
  * "Start/End Dates" + "Total Days Watched"

* Recommendations (for best display, not required):
  * Enable "Type".
  * If using "Numbers", enable "Image". 
        
### 2. Then you want to go over to [this page](https://myanimelist.net/ownlist/style) and do one of two things:
1. Click on the image of the theme you have selected
2. Select a different theme and click it's image (so you can let the theme you were previously using unchanged)

### 3. You should now be in a page that looks like this. Here you want to turn off the cover and background images and save.

![menu](/images/Customize_Menu.png)

### 4. On the same page you want to find the custom CSS box underneath the "Add Custom CSS" header. Make sure it is empty, then copy-paste this code into the box.
```css
@\import "https://valeriolyndon.github.io/MAL-Public-List-Designs/Clarity%20Theme/Theme%20-%20Compressed.css";

@\import "https://valeriolyndon.github.io/MAL-Public-List-Designs/Clarity%20Theme/Mod%20-%20Dark%20Mode%20Compressed.css";

/*POP-UP Images on image hover*/
@\import "https://malscraper.azurewebsites.net/covers/anime/YOURUSERNAME/presets/dataimagelinkbefore";
@\import "https://valeriolyndon.github.io/MAL-Public-List-Designs/Clarity%20Theme/Mod%20-%20Hover%20Image%20On%20Circle%20Compressed.css";

/*tmigas' custom changes*/
@\import "https://tmigas.github.io/MAL_CSS/tmigas_MAL_COMPRESSED.css";


body { --name: "\a  YOURUSERNAME"; }
body { --avatar: url(URLHERE); }

body { --character: none; }
```
Here there are 3 things to keep in mind. 
1. First you need to change YOURUSERNAME to your MAL user name in the middle of the first import of the POP-UP images area 
2. Then also change the __body { --name: "\a  YOURUSERNAME"; }__ line of code, on this one if you want you can play around with the spaces and even use "\a" to change lines as long as keep yourself between the "".
3. Lastly in the line after the previous you want to change URLHERE to your MAL's avatar (if that's the image you choose to use), for help with this you can follow these steps:
   1. Go to your profile.
   2. Right click your profile image and select "copy image address" (or similar, it may be worded differently in your browser!). The dialogue looks like this (left image: Chrome, right image: Firefox).


![profile_picture](/images/profile_picture.png)

### 5. With this you just need to click SAVE and you're all done with the basic. If you want you can close this guide, but if you want to costumize your images I'll teach you how next but keep in kind that unless specified all the code goes in the bottom.

### 6. There are 3 main things you can costumize: The Avatar, The Banner, or add a character over the right side of the Banner.
First, the Avatar, since we already set your avatar the only thing left to costumize would be if you wanted to change it deppending on which page you are, if you do, you want to replace this:
```css
body { --avatar: url(URLHERE); }
```
with
```css
/*-S-T-A-R-T--------------------*\
|           AVATAR               |
\*------------------------------*/
[data-query*="status\":7"] { --avatar: url(URLHERE); }
/* Watching */
[data-query*="status\":1"] { --avatar: url(URLHERE); }
/* Completed */
[data-query*="status\":2"] { --avatar: url(URLHERE); }
/* Onhold */
[data-query*="status\":3"] { --avatar: url(URLHERE); }
/* Dropped */
[data-query*="status\":4"] { --avatar: url(URLHERE); }
/* Planned */
[data-query*="status\":6"] { --avatar: url(URLHERE); }
/*------------------------E-N-D-*/
```
For the Banner, if you want just to change it to a different one you want to add this:
```css
body { --banner: url(URLHERE); }
```
but if like before you want it to be differente deppending on which page you are:
```css
/*-S-T-A-R-T--------------------*\
| Per-Category Banner Image      |
\*------------------------------*/
/* All Anime */
[data-query*='status":7'] { --banner: url(URLHERE); }
/* Watching/Reading */
[data-query*='status":1'] { --banner: url(URLHERE); }
/* Completed */
[data-query*='status":2'] { --banner: url(URLHERE); }
/* Onhold */
[data-query*='status":3'] { --banner: url(URLHERE); }
/* Dropped */
[data-query*='status":4'] { --banner: url(URLHERE); }
/* Planned */
[data-query*='status":6'] { --banner: url(URLHERE); }
/*------------------------E-N-D-*/
```
Lastly, if you want to add a character over the banner you want to replace the following:
```css
body { --character: none; }
```
with
```css
body { --character: url(URLHERE); }
```
or with this if you want one different for every page
```css
/*-S-T-A-R-T--------------------*\
| Per-Category Character Image   |
\*------------------------------*/
/* All Anime */
[data-query*='status":7'] { --character: url(https://i.imgur.com/JG3cHc5.png); }
/* Watching/Reading */
[data-query*='status":1'] { --character: none; }
/* Completed */
[data-query*='status":2'] { --character: url(https://i.imgur.com/U6zIYcT.png); }
/* Onhold */
[data-query*='status":3'] { --character: none; }
/* Dropped */
[data-query*='status":4'] { --character: none; }
/* Planned */
[data-query*='status":6'] { --character: url(https://i.imgur.com/BYYJO0l.png); }
/*------------------------E-N-D-*/
```
### 7. There's also a small teak you might find usefull if you use some kind of dark mode from the browser or an extension:
First let's check if you need it, click on preview or save, then click the quick add or try to edit an anime, if the window appears white like on the left you will need to add an extra line

![dark_mode](/images/dark_mode.png)

if you need it, here's the line you should add at the bottom:
```css
body[data-owner="1"] #fancybox-frame { filter: none; }
```

### 8. Save!!     ...and done, you're good to go... almost, first you need to know which tags have special appearences right :)?.
[List of tags](https://docs.google.com/spreadsheets/d/18JZI3sOT2gPteI5RmJQO46VVKMbtHdq0zc3qsDwHU-E/edit?usp=sharing)


### 9. If you have questions, need help or want to suggest something here are a few ways of reaching me:
* [twitter](https://twitter.com/tmigaskino)
* [MAL](https://myanimelist.net/profile/tmigas)
* tmiguelkino@gmail.com

