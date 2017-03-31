# TheStreet Keystone FontIcons
Font icon repo for TheStreet
As long as your file structure is the same as TST-NG these instructions should work otherwise editing the urls from the _font-icons.scss may be necessary

<h3>Adding font-icons font to your project:</h3>

To manually add the font-icon library to a project:
<ol>
<li>Download the entire font-icons dir containing the font files to the CMS-TAGS/grails-app/assets/stylesheets/fonts</li>
<li>Download the _font-icons.scss to CMS-TAGS/grails-app/assets/stylesheets/styles/modules</li>
</ol>

To install use npm:
<ol>
<li>go to the vendor folder cms-tags/grails-app/assets/vendor</li>
<li>run <code>npm install ks-fonticons</code></li>
<li>The postinstall script will auto-overwrite the fonts and _font-icons.scss</li>
</ol>

<h2>To add/edit/delete the fonts:</h2> 
<ol>
<li>There two main steps to udating the font library</li>
<li>Update the master files which will update the files directly handling the font icons</li>
<li>Update the gh-pages branch which will update the font-icon reference page of the style-guide</li>
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
</p>
<li>Upload the new _font-icons.sccs to the assets dir of the master branch of this repo (ks-fonticons)</li>
<li>Upload the new font files in the new fonts folder to the dir fonts/fonticons/ of the master branch of this repo (ks-fonticons)</li>
<li>Be sure to increment the version number of the repo in the package json (you cna simply do this by editing the package.json from the repo editor</li>
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
    
</li>
<li>Rename the demo.hmtl file to index.html</li>
<li>Then upload it to gh-branch of ks-fonticons repo</li>
<li>Now locate the _font-icons.scss file you uploaded to this the master branch of thei repo and rename it: font-icons.css</li>
<li>Then upload it to gh-branch of ks-fonticons repo into the assets folder</li>
<li>You can see the showcase page for the new fonts you just edited here: https://dondmcg.github.io/</li>
<li>Just clikc the dropdown and select "Font-icons"</li>
</ol>
