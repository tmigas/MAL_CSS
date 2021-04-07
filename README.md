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
    @\import "https://valeriolyndon.github.io/MAL-Public-List-Designs/Clarity%20Theme/Theme%20-%20Compressed.css";

    @\import "https://valeriolyndon.github.io/MAL-Public-List-Designs/Clarity%20Theme/Mod%20-%20Dark%20Mode%20Compressed.css";

    /*POP-UP Images on image hover*/
    @\import "https://malscraper.azurewebsites.net/covers/anime/YOURUSERNAME/presets/dataimagelinkbefore";
    @\import "https://valeriolyndon.github.io/MAL-Public-List-Designs/Clarity%20Theme/Mod%20-%20Hover%20Image%20On%20Circle%20Compressed.css";

    /*tmigas' custom changes*/
    @\import "https://tmigas.github.io/MAL_CSS/tmigas_MAL_COMPRESSED.css"

    body { --name: "\a  YOURUSERNAME"; }
