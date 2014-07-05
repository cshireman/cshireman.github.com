---
layout: post
title: "My Experience Converting Wordpress To Jekyll"
description: "Now that I have converted everything from my wordpress blog over to my Jekyll blog, I have determined that it is a very error prone process.  Even so, perhaps listing the steps for producing a properly functioning Jekyll blog following the export of my wordpress posts will help someone along the way."
category: blogging
tags: [blogging,jekyll,wordpress]
---
{% include JB/setup %}

Happy Independence Day!  

Now that I have converted everything from my wordpress blog over to my Jekyll blog, I have determined that it is a very error prone process.  Even so, perhaps listing the steps for producing a properly functioning Jekyll blog following the export of my wordpress posts will help someone along the way.

I will not go into great detail, I will only list my steps and point out some of my pain points.  Just for the sake of reference, I have a Mac Book Pro with OSX Mavericks.  Your configuration may vary.

1) Install Jekyll and get setup with Github pages.  This wasn't all that difficult, although I can see it being a stumbling block for non-technical users.  I decided to use jekyll-bootstrap for my blog, mostly for the easy templating ability.  You can get detailed steps here: [Jekyll Bootstrap](http://jekyllbootstrap.com)

2) Export your wordpress posts to an XML file on your local drive.  You can do this by logging into your wordpress admin account, selecting Tools, then Export.  Make sure to export everything as that will be easiest.  Save the file to your local drive in a convenient place.

3) Install the jekyll-import ruby gem.  You can do that by running this command in the terminal:

	gem install jekyll-import

4) Next, run this command in the same directory as your exported wordpress.xml file.  Please note you may need to alter the command to include the proper filename of your xml file:

	ruby -rubygems -e 'require "jekyll-import";
    JekyllImport::Importers::WordpressDotCom.run({
      "source" => "wordpress.xml",
      "no_fetch_images" => false,
      "assets_folder" => "assets"
    })'

5) Copy the newly created assets and _posts folders to your local jekyll install.  I didn't want the pages from the old site, but you can copy those too if you like.

6) Update your newly created posts to use the proper paths for the images.  I was able to do this with a single replace command.

7) You may need to update your index.md file in your jekyll install to allow for html.  The newly created posts in your _posts directory will be HTML, not markdown.  So this is a great time to test your import by running:

	jekyll serve

8) At this point you will likely get some errors from jekyll, thankfully mine were simple path errors or characters that should have been escaped.  If you are lucky, everything will go smoothly.  

9) Open your favorite web browser and point it to http://localhost:4000.  Check to make sure your blog is the way you want it.  If not, you will need to tweak the templates, layouts, and any other files you see fit to make it look the way you want it.

10) Rinse and repeat.  Keep tweaking and making changes until you have something that you like.  Since this is a personal preference, I can't go into too much detail.  

11) Last step!  Run these commands:

	git add .
	git commit -m "Finishing wordpress import"
	git push origin master

That's all folks, your blog should now include all the wordpress posts from your previous blog.  There are a couple of gotchas that I still haven't worked out:

1) The doesn't seem to be a way to get the featured images out of wordpress and into jekyll.  You will need to add them manually.

2) Given this process, the actual image link references still use the original wordpress paths.  This means that I currently have two versions of the same image on my site.  While this is not ideal, I wanted to get this done in less than a day and didn't want to go back over all my posts.

