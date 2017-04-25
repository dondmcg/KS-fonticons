# TheStreet Keystone FontIcons
Font icon repo for TheStreet
As long as your file structure is the same as TST-NG these instructions should work otherwise editing the urls from the _font-icons.scss may be necessary

<h3>Adding font-icons font to your project:</h3>

To manually add the font-icon library to a project:
<ol>
<li>Download the entire font-icons dir containing the font files to the CMS-TAGS/grails-app/assets/stylesheets/fonts</li>
<li>Download the _font-icons.scss to CMS-TAGS/grails-app/assets/stylesheets/styles/modules</li>
<li>Commit and merge these changes in CMS-Tags project to your local branch (branch from develop), making sure you have incremented the Build.Config version number for CMS-TAGS then open a Pull Request for merge to develop branch</li>
</ol>

To install use npm:
<ol>
<li>go to the vendor folder cms-tags/grails-app/assets/vendor</li>
<li>run <code>npm install ks-fonticons</code></li>
<li>The postinstall script will auto-overwrite the fonts and _font-icons.scss</li>
<li>Commit and merge these changes in CMS-Tags project to your local branch (branch from develop), making sure you have incremented the Build.Config version number for CMS-TAGS then open a Pull Request for merge to develop branch</li>
</ol>

<h2>To add/edit/delete the fonts:</h2> 
<p>There two main steps to udating the font library</p>
<ol>
<li>Update the library master files which will handle the adding or deleteing of font icons</li>
<li>Update the gh-pages branch which will update the font-icon reference page of the font style-guide</li>
</ol>


<h3>Updating font library master branch files</h3>

<ol>
<li>Download the selection.json file from this github repo</li>
<li>Upload the selection.json file to icomoon.io app</li>
<li>Add, edit or delete fonts (keep in mind the fonts are named the same as that of the svg file name used so please follow these conventions:
<ol>
<li>Use dashes instead of underscores when naming svg files</li>
<li>All fonts are prefixed with "font-icons-" so please refrain from using these words in the name ie: "share-icon" becomes "font-icon-share-icon"  there fore better naming conventions would be: "share.svg" or share-arrow.svg"</li>
</ol>
</li>
<li>Then click "Generate Font"</li>
</ol>

After downloading the newly created font there are four files or sets of files to be concerned with:
<ol>
<li>style.css (will become _font-icons.scss and font-icons.css)</li>
<li>demo.html (will become index.html for the gh-pages)</li>
<li>selection.json (will replace initial selection.json)</li>
<li>package.json (from this repo to increment the version number)</li>
<li>four font files inside the fonts directory</li>
</ol>
With this in mind proceed to...
<ol>
<li>From the resulting files locate the style.css file and the fonts dir</li>
<li>Edit the resulting style.css to match the _font-icons.scss file and rename it as _font-icons.scss</li>
<li><p>
To edit the style.css simply make sure the font face declaration at the top of the page matches:
</p>
<pre>@font-face {
  font-family: 'font-icons';
  src:  url('../fonts/font-icons/font-icons.eot?trcws1');
  src:  url('../fonts/font-icons/font-icons.eot?trcws1#iefix') format('embedded-opentype'),
    url('../fonts/font-icons/font-icons.ttf?trcws1') format('truetype'),
    url('../fonts/font-icons/font-icons.woff?trcws1') format('woff'),
    url('../fonts/font-icons/font-icons.svg?trcws1#font-icons') format('svg');
  font-weight: normal;
  font-style: normal;
  }</pre>
</li>
<li>After cloning a local repo for ks-font-icons</li>
<li>Upload the new _font-icons.sccs to the assets dir of the master branch of this repo (ks-fonticons)</li>
<li>Upload the new font files in the new fonts folder to the dir fonts/fonticons/ of the master branch of this repo (ks-fonticons)</li>
<li>Be sure to increment the version number of the repo in the package json (you can simply do this by editing the package.json from the repo editor</li>
<li>In the terminal on your machine navigate to the ks-fonticons local repo</li>
<li>From this dir run <pre>$ npm publish</pre> to update the registry to the new package version number</li>
<li>At this point update the project by refering to the instructions above "Adding font-icons font to your project"</li>
</ol>

<h3>Updating gh-pages branch files</h3>

<ol>
<li>First locate the demo.html and update the head info<br>
<pre>&#x3C;head&#x3E;
    &#x3C;meta charset=&#x22;utf-8&#x22;&#x3E;
    &#x3C;title&#x3E;Font Icons&#x3C;/title&#x3E;
    &#x3C;meta name=&#x22;description&#x22; content=&#x22;An Icon set for the street&#x22;&#x3E;
    &#x3C;meta name=&#x22;viewport&#x22; content=&#x22;width=device-width, initial-scale=1&#x22;&#x3E;
    &#x3C;link rel=&#x22;stylesheet&#x22; href=&#x22;assets/demo.css&#x22;&#x3E;
    &#x3C;link rel=&#x22;stylesheet&#x22; href=&#x22;assets/font-icons.css&#x22;&#x3E;&#x3C;/head&#x3E;</pre>
</li>
<li>Then remove the test code at the bottom<br>
what appears between:
<pre>
&#x3C;!--[if gt IE 8]&#x3E;&#x3C;!--&#x3E;
</pre>
AND
<pre>
&#x3C;!--&#x3C;![endif]--&#x3E;
</pre>
<p> as well as the demo-script.js and icomoon link</p>
</li>
<li>Rename the demo.html file to index.html</li>
<li>Now locate the _font-icons.scss file you uploaded to this the master branch of the repo and duplicate it and rename the dupe: font-icons.css</li>
<li>Then upload both files as well as all the new fonts to gh-pages branch of ks-fonticons repo, note though that the font-icons.css goes into the assets folder and the fonts go into the fonts/font-icons/ folder</li>
<li>After committing to gh-pages branch the styleguide will be updated.</li>
<li>You can see the showcase page for the new fonts you just edited here: https://dondmcg.github.io/</li>
<li>Just click the dropdown and select "Font-icons"</li>
</ol>
