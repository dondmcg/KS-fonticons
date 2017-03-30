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
<li>package.json (from this repo)</li>
<li>four font files inside the fonts directory</li>
</ol>

<ol>
<li>From the resulting files locate the style.css file and the fonts dir</li>
<li>Edit the resulting style.css to match the _font-icons.scss file and rename it as _font-icons.scss</li>
<li>Upload the new _font-icons.sccs to the appropriate place in this repo</li>
<li>Upload the new font files in the new fonts folder to the dir fonts/fonticons/ in this repo</li>
<li>Be sure to increment the version number of the repo in the package json</li>
<li>Follow the instructions above to add the font-icon library to a project</li>
<li>Update the gh-pages branch so that the demo page reflects the changes</li>
</ol>

<h3>Updating gh-pages branch files</h3>

