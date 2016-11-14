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
<li>upload the selection.json file to icomoon.io app</li>
<li>add, edit or delete and then click "Generate Font"</li>
<li>edit the resulting style.css to match the _font-icons.scss file</li>
<li>follow the instructions above to add the font-icon library to a project</li>
<li>update the gh-pages branch so that the demo page reflects the changes</li>
</ol>
