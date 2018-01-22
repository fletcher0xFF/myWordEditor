# myWordEditor

A simple silo-free blogging tool that creates beautiful essay pages. 

Here's an <a href="http://myword.io/users/davewiner/essays/030.html">example</a> of the kind of page you can create with MyWord Editor.

And the <a href="http://scripting.com/2015/03/23/mywordEditorIsOpenSource.html">blog post</a> announcing the release of MyWord Editor in open source.

#### Demo app

Here's the <a href="http://myword.io/editor/">demo app</a> for this project, MyWord Editor.

You can set up your own blogging environment and use it to host your writing and for other people, your friends, colleagues, members of a club, whatever you like. 

#### It's radical software

These days blogging tools try to lock you into their business model, and lock other developers out. I don't  want to operate a free public blogging tool and lock users in and make them dependent on me. Instead, I want to learn from thinkers and writers and developers.

So MyWord Editor is radically <a href="http://scripting.com/2015/03/19/mywordEditorWillBeSilofreeFromTheStart.html">silo-free</a>. 

#### How to clone this

This app runs on the user's computer, in a browser. It's a JavaScript app. It communicates via a simple <a href="http://api.nodestorage.io/api.js">API</a>, with a <a href="https://github.com/scripting/nodeStorage">nodeStorage</a> server, that uses Twitter for identity and Amazon S3 for storage. That server, like the app, is open source. The first part of creating your own blogging system is to set up a nodeStorage server. 

Once you've done that, download the contents of the myWordEditor repository, and put it in a folder that's publicly accessible over the web. I like using S3 buckets, but you could put it in a folder on an Apache or nginx server. 

Edit the config.json file so that the <i>urlTwitterServer</i> string is the URL of your nodeStorage server. 

You can also change the default image for your users' blog posts, or you can leave it as-is, with a nice picture from Wikipedia of the Grateful Dead. 

Test the installation by logging on. Follow the <a href="http://myword.smallpict.com/2015/03/06/welcomeToMywordEditor.html">instructions</a> on the MyWord Editor blog.

#### Updates

##### Fork -- Jan. 20, 2018 by AF

A new fork has begun. The first official release will be version 0.7.4 and is expected to be complete in 2-3 weeks.

##### v0.73 -- Sept. 9, 2017 by DW

Changed URLs in includes in &lt;head> section of index.html to not be specific to HTTP, so that <a href="https://github.com/scripting/myWordEditor/issues/4">people</a> can run their nodeStorage servers behind HTTPS.

##### v0.72 -- July 27, 2015 by DW

Added <s>strikethrough</s> button to the toolbar, demonstrating that we can add items to the toolbar. They come from <a href="https://github.com/yabwe/medium-editor#all-buttons">this list</a>. 

##### v0.71 -- July 27, 2017 by DW

Add Facebook and Twitter metadata to the &lt;head> section of the home page.

Changed the default value of the <i>flAutoPublish</i> setting from false to true. This is the behavior I demo in the <a href="https://www.youtube.com/watch?v=AdddswiXm5g&feature=youtu.be">video</a>, and it seems to be what people expect. 

##### v0.70 -- July 25, 2015 by DW

By default Disqus comments are now on. You can turn them off in the Settings dialog. 

##### v0.69 -- July 25, 2015 by DW

Added <a href="http://walkthrough.rsscloud.co/">rssCloud</a> support to the RSS feed produced by MWE. 

The feature can be turned on in <a href="https://github.com/scripting/myWordEditor/blob/master/config.json">config.json</a>, if you're running your own MWE. 

I'm using <a href="http://blog.andrewshell.org/what-is-rsscloud/">Andrew Shell's</a> rssCloud <a href="http://blog.andrewshell.org/rebooting-rsscloud/">server</a> for notification, rsscloud.io.

Here's my <a href="http://myword.io/users/davewiner/rss.xml">RSS feed</a>, as an example.

##### v0.67 -- July 24, 2015 by DW

We now have a beautiful editor, integrated, <a href="https://github.com/yabwe/medium-editor">medium-editor</a>. Problem solved. :-)

You can read about the update in this <a href="http://myword.io/users/davewiner/essays/045.html">note</a>, and a <a href="http://scripting.com/2015/07/24/mywordEditorGetsMoreBeautiful.html">blog post</a>. 

##### v0.64 -- April 3, 2015 by DW

Run config.startupCode at startup. See <a href="http://myword.smallpict.com/2015/04/03/codeThatRunsAtStartup.html">blog post</a> for details.

##### v0.63 -- April 2, 2015 by DW

Took a step toward <a href="http://myword.smallpict.com/2015/04/02/towardEditorPlugins.html">editor plug-ins</a>. 

##### v0.62 -- April 1, 2015 by DW

Support for Disqus comments. See this <a href="http://myword.smallpict.com/2015/04/01/disqusCommentsInMyword.html">blog post</a> for details.

##### v0.61 -- March 31, 2015 by DW

Add scalars from appConsts and appPrefs to the pagetable in the rendered page. This allows scripts running in the page to know the title of the site, the version of MWE that created the page, etc.

In the title of essay pages, we use the author's name if it's available instead of the name of the product. So a story might say "Jordan Jones: What I want for Christmas" instead of "MyWord Editor: What I want for Christmas". 

##### v0.60 -- March 30, 2015 by DW

This is the first release of MWE with <a href="http://myword.smallpict.com/2015/03/30/templatesInMyword.html">template</a> support. Be sure to read the note about breakage on that page. Any work you do with templates now is likely to break. 

##### v0.59 -- March 27, 2015 by DW

First source release of the JavaScript code and CSS styles used in the rendered pages. Explained in this <a href="http://myword.smallpict.com/2015/03/27/mywordEditorV059.html">blog post</a>. 

##### v0.58 -- March 27, 2015 by DW

The *Open file* command in the Editor menu is replaced by a new History menu. Explained in this <a href="http://myword.smallpict.com/2015/03/27/theHistoryMenu.html">blog post</a>.

##### v0.57 -- March 26, 2015 by DW

There were lots of debugging calls to console.log that displayed huge data structures. I quieted them down, so we get simpler readouts from the console, now that this code isn't so new. Changed the <i>urlTemplateFile</i> constant to be a relative URL, relative to the folder MWE is running from. That way I can change the template on my server without changing it on everyone's. Still more of this kind of factoring to do. Must move carefully (slowly).

##### v0.56 -- March 26, 2015 by DW

New supported value in config.json -- googleAnalyticsAccount. If specified, we use it in <a href="https://github.com/scripting/myWordEditor/blob/master/lib/ga.js">ga.js</a> to make calls to Google Analytics. 

##### v0.55 -- March 26, 2015 by DW

Change notes in this <a href="http://myword.smallpict.com/2015/03/26/mywordEditorV055.html">blog post</a>.

##### v0.54 -- March 24, 2015 by DW

A new command in the Editor menu: <i>Publish all posts.</i> After confirmation, it opens each of your posts and does exactly what clicking on the Publish button would do. I added this feature because I wanted a quick way to re-generate all the files. It'll be useful if there's a template change, or other change that requires a complete rebuild of a blog.

Also improved the <a href="http://scripting.com/2015/03/24/errorDialog.png">error dialog</a> on startup, if there was an error connecting to the server, it would report the problem as the user not being whitelisted. Usually the problem is the URL of the nodeStorage server was not correctly specified. I got bit by this myself. We needed a better message here. 

##### v0.53 -- March 24, 2015 by DW

In addition to generating an HTML file for each essay, we also generate a JSON file. <a href="http://myword.io/users/davewiner/essays/017.json">Example</a>. I think this will be generally useful, I want to use it immediately to try to create a home page essay browser, using snap.js. There's a corresponding <a href="https://github.com/scripting/myWordEditor/blob/master/lib/buildrss.js#L146">element</a> in the RSS feed, called &lt;source:linkJson>. 

#### Support

Please ask questions or report bugs on the <a href="https://github.com/fletcher0xFF/myWordEditor/issues">issues page</a> for this GitHub project.
