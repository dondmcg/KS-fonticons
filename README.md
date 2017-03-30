# TheStreet Keystone FontIcons
Font icon repo for TheStreet
As long as your file structure is the same as TST-NG these instructions should work otherwise editing the urls from the _font-icons.scss may be necessary

To manually add the font-icon library to a project:
<ol><li>Download the entire font-icons dir containing the font files to the CMS-TAGS/grails-app/assets/stylesheets/fonts</li>
<li>Download the _font-icons.scss to CMS-TAGS/grails-app/assets/stylesheets/styles/modules</li>
</ol>

To install use npm:
<ol>
<li>go to the vendor folder cms-tags/grails-app/assets/vendor</li>
<li>run <code>npm install ks-fonticons</code></li>
<li>The postinstall script will auto-overwrite the fonts and _font-icons.scss</li>
</ol>

To edit the fonts: 
<ol>
<li>There two main steps to udating the font library</li>
<li>Update the master files which will update the files directly handling the font icons</li>
<li>Update the gh-pages branch whihc will update the font-icon reference page of the style-guide</li>
</ol>


<h3>Updating master branch files</h3>

<ol>
<li>Download the selection.json file from this github repo</li>
<li>Upload the selection.json file to icomoon.io app</li>
<li>Add, edit or delete and then click "Generate Font"</li>
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
<p>
To edit the style.css simply make sure the font face declaration at the top of the page matches:<br><br>
@font-face {
  font-family: 'font-icons';
  src:  url('../fonts/font-icons/font-icons.eot?trcws1');
  src:  url('../fonts/font-icons/font-icons.eot?trcws1#iefix') format('embedded-opentype'),
    url('../fonts/font-icons/font-icons.ttf?trcws1') format('truetype'),
    url('../fonts/font-icons/font-icons.woff?trcws1') format('woff'),
    url('../fonts/font-icons/font-icons.svg?trcws1#font-icons') format('svg');
  font-weight: normal;
  font-style: normal;
  }
</p>
<li>Upload the new _font-icons.sccs to the assets dir of this repo</li>
<li>Upload the new font files in the new fonts folder to the dir fonts/fonticons/ in this repo</li>
<li>Be sure to increment the version number of the repo in the package json</li>
<li>In the terminal navigate to the ks-fonticons local repo</li>
<li>From this dir run $ npm publish to update the registry to the new package version number</li>
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
&#x3C;!--[if gt IE 8]&#x3E;&#x3C;!--&#x3E;
    &#x3C;div class=&#x22;mhl clearfix mbl&#x22;&#x3E;
        &#x3C;h1&#x3E;Font Test Drive&#x3C;/h1&#x3E;
        &#x3C;label&#x3E;
            Font Size: &#x3C;input id=&#x22;fontSize&#x22; type=&#x22;number&#x22; class=&#x22;textbox0 mbm&#x22;
            min=&#x22;8&#x22; value=&#x22;48&#x22; /&#x3E;
            px
        &#x3C;/label&#x3E;
        &#x3C;input id=&#x22;testText&#x22; type=&#x22;text&#x22; class=&#x22;phl size1of1 mvl&#x22;
        placeholder=&#x22;Type some text to test...&#x22; value=&#x22;&#x22;/&#x3E;
        &#x3C;div id=&#x22;testDrive&#x22; class=&#x22;font-icon-&#x22;&#x3E;&#x26;nbsp;
        &#x3C;/div&#x3E;
    &#x3C;/div&#x3E;
    &#x3C;!--&#x3C;![endif]--&#x3E;
    &#x3C;div class=&#x22;bgc1 clearfix&#x22;&#x3E;
        &#x3C;p class=&#x22;mhl&#x22;&#x3E;Generated by &#x3C;a href=&#x22;https://icomoon.io/app&#x22;&#x3E;IcoMoon&#x3C;/a&#x3E;&#x3C;/p&#x3E;
    &#x3C;/div&#x3E;

    &#x3C;script src=&#x22;demo-files/demo.js&#x22;&#x3E;&#x3C;/script&#x3E;</li>
<li>Rename the demo.hmtl file to index.html</li>
<li>Then upload it to gh-branch of ks-fonticons repo</li>
<li>Now locate the _font-icons.scss file you uploaded to this the master branch of thei repo and rename it: font-icons.css</li>
<li>Then upload it to gh-branch of ks-fonticons repo into the assets folder</li>
</ol>
With this in mind proceed to...
<ol>
