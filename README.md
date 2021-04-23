# Welcome!

Welcome to the Collection Builder Site Building Guide!  This guide will walk you through the steps required to build your very own basic Collection Builder site using GitHub pages.  In order to follow through this tutorial, you will need:

1. A GitHub account
2. Some content that you want to exhibit (jpeg's, pdf's, mp3 files, mp4 files, etc.)
3. Metadata for each of those items

Once you have your account and materials ready you can get started.

---

# Step 1 - Get your Git in Gear

The first step to building a Collection Builder site using GitHub pages is to clone all of the code that works behind the scenes to turn your metadata into an exhibit.  To do this, go to https://github.com/CollectionBuilder/collectionbuilder-gh.  You will see a repository containing all sorts files and folders that make up Collection Builder.  What you want to do is create a repository of your own and copy all of those files into it.  Luckily our friends on the Collection Builder team have made this very easy by turning their repository into a template that can be copied easily.

To copy the contents of the repository, click on the green "Use this template" button at the top.  Next, you will need to give a name to your repository.  This will determine what the URL for your Collection Builder Exhibit will be so make sure to pick something that makes sense for your project.  Once you have a good title, check that the bubble for "Public" is checked and then click the green "Create repository from template" button.

Just like that you now have your very own repository with all of the code needed to build a Collection Builder Exhibit!

---

# Step 2 - Make and Manage your Metadata

The next thing you need to do is prepare your content that will be displayed in your Collection Builder Exhibit.  The most important part of your entire site is the metadata csv file.  This is the file that Collection Builder will use to build all of the item pages, visualizations, and more.  The structure of the metadata file is very impotant as there are some fields that are absolutely required in order for your site to work.  The steps below will help you build a clean, functional metadata file.

1. Start by either creating your own csv file (In Excel, Google Sheets, etc) or by downloading the template from [HERE](https://brocku-my.sharepoint.com/:f:/g/personal/dbrett_brocku_ca/EpNSItFDGLNEmeV6FTtwC1UBiDJ_otCzUyVWZa4_9Emipw?e=0ROcBg).
2. Next you will decide what metadata fields you will include.  You can add as many fields as you want to your metadata file but there are four fields that you MUST include in order for Collection Builder to work.  They are: 
     - objectid (A unique identifier for each item that cannot contain space or special characters)
     - title (This is a descriptive name for the item)
     - format (This describes what type of media the item is using [MIME type standards](https://www.iana.org/assignments/media-types/media-types.xhtml). Some of the most commonly used fortmats are image/jpeg, application/pdf, audio/mp3, video/mp4)
     - filename (this is the name of the item that the metadata is for.  This field must match perfectly to the name of the file eg. demo1.jpg or analysis1.pdf and cannot contain special characters or spaces so make sure your filenames also adhere to this rule)
3. In addition to the four mandatory fields there are certain fields that need to be included if you want to use some of the most interesting functions of Collection builder.  Each of these functions represent a page on your collection builder site.
     - The Map Page.  In order to use the map page feature of Collection builder you will need to include fields for latitude and longitude in your metadata file.
     - The Timeline Page.  In order to use the timeline page feature of Collection Builder you will need to include a date field (date format can be yyyy, yyyy-mm, or yyyy-mm-dd)
     - The Subject Wordcloud page.  In order to use the subject wordcloud page feature of Collection Builder you will need to include a subject field.  Subjects can be anything you want and you can assign multiple subjects to an item by seperating them with a semicolon (;).
     - The Location Wordcloud Page .  In order to use the location wordcloud page feature of Collection Builder you will need to include a location field.
4. Feel free to add any other metadata fields that you think may be relevant (description, creator, language, etc) keeping in mind that field names must be in lowercase and not contain any characters other than letters and numbers (no spaces allowed!).
5. Fill in the information for all of your items and them save your file.  (Make sure not to leave any fields blank and that the name for your csv file does not include any spaces)
6. Now that you have a fully prepped metadata file to go along with all of the item you want to exhibit, you will need to get everything onto GitHub.
     - For the metadata file, you will go to the main page of your GitHub repository and click on the "\_data" folder.  Next you will click the "Add file" dropdown in the top right and select "Upload files".  Now you can either drag your metadata file into the box on the page or you can click the "choose your files" option to open a file explorer window to find and select your file.  Once you have added your metadata file (the name of the file will appear below the box on the screen), click on the green "Commit Changes" button at the bottom of the page.
     - For your images, pdf's and other items that were recorded in the metadata file, you will first click on the "objects" folder from the main page of your repository.  Next, click on the "Add file" dropdown in the top right and select "Upload files".  Now you can either drag your files into the box on the page or you can click the "choose your files" option to open a file explorer window to find and select your files.  Once you have added all of your files, click on the green "Commit Changes" button at the bottom of the page.

And with that your items and metadata are ready to go!  In the future if you decide you want to add any more items you simply have to adjust the metadata file and add the new item to the objects folder and it will appear on your exhibit!

---

# Step 3 - Supply your Site Settings

Now that your items and metadata are all set, the next task it to set up your sites settings.  The settings for your site are controlled by a special file called \_config.yml.  This file can be found on the home page of your repository.  Click on the \_config.yml file to be taken to the file viewer and then click on the pencil icon on the right-hand side to open the file edit view.  Now you will work your way through each of the settings and make adjustments as needed on the lines that don't start with a hashtag (\#):

URL Settings

- "url"  This setting points Collection Builder to your GitHub pages base url.  The format is https://YOURGITHUBNAME.github.io.  An example of what this line will look like is: 
     - url: https://BrockDSL.github.io
- "baseurl"  This setting points Collection Builder to the repository that your exhibit is in.  All you need to do here is copy the name of your repository (including capital letters and special characters) then put a / in front of it.  An example of what this line will look like is:
     - baseurl: /Demo_Exhibit
- "source-code"  This setting is filled with the url to the main page of your GitHub repository.  An example of what this line will look like is: 
     - source-code: https://github.com/BrockDSL/Demo_Exhibit

Site Level Settings

- "title"  This is the title of your exhibit as it will be displayed on the home page of your site.  Pick a name that makes sense and type it as you want it to be show (No need to add hyphens or underscore here).  An example of what this line will look like is: 
     - title: My Amazing Demo Exhibit

- "tagline"  This is the short line of text that will appear at the top of some pages on your site.  An example of what this line will look like is:
     - tagline: A showcase of all my favorite things 

- "description"  This is the short description of your exhibit that can show up in search results.  This should be in quotation marks and be kept to under 160 characters to keep things tidy.  An example of what this line will look like is: 
     - description: "This demo exhibit is full of my favorite things that I want to share with the world"

- "author"  This is the spot where you put your GitHub name so anyone who looks at the exhibit knows who made it.  An example of what this line will look like is: 
     - author: BrockDSL

Collection Setting

- "metadata"  This is where you let Collection Builder know the name of the file containing your metadata (use the name of the file without the .csv at the end).  An example of what this line will look like is: 
     - metadata: metadatafilename

Once you are happy with all of the changes you have made, click on the green "Commit Changes" button at the bottom of the page.

And thats all of the top level site settings!  If you want you can add google analytics to your exibit by entering you google analytics ID but other than that you can leave everything else as it is.

---

# Step 4 - Adding some About Attributes

So with the settings established you are just about ready for the big reveal!  The last thing you are going to do before making your site live and taking a look at it is to add some information to the about page.  From the main page of your repository, click on the "pages" folder.  From here you will open the file called about.md and click the pencil on the right-hand side to start editing.

This page is written in a language called markdown and may look a bit alarming if you are not familiar with the markdown syntax.  But don't fear!  Most of whats on this page can be ignored.  Make sure that you leave everything on lines 1-14 as is, after that you can do whatever you want!  The section from lines 15-23 is the part that you will remove and replace with whatever content that you want.  The bit of code at the end will add a section to the end of your about page that describes all of the advanced features that you can add to the page so if you are interested in these features, leave lines 24-26 until after your site goes live.

So lets get some info added to this page:

1. Delete everything from lines 15-23 (or from lines 15 to the bottom if you don't want the advance features text on your about page)
2. In the space you just made start adding some text about your exhibit.  If you want a header you can use the markdown syntax of ## YOUR HEADER.  For more advanced markdown features like lists and bullet points check out the [Markdown Cheatsheet](https://www.markdownguide.org/cheat-sheet/)
3. Once you are happy with your About page text (you can always come back and change it later) then click the green "Commit Changes" button at the bottom of the page.

---

# Step 5 -

Now it time to make your site live and take a look at it!  Go back to the main page of your repository and click on the settings tab in the top menu.  There are many different settings in a GitHub repository and the one we want is called "Pages".  In the menu on the left click on "Pages" to open up the GitHub Pages settings.  You will see a section called "Source" with a dropdown button that says "None".  Open this dropdown and select "main" then click the save button.  You will see a message letting you know that your site is being built and the address that you can find it at.  This process can take a minute or two so go grab a snack or a glass of water and then when you come back go to the web adress for your site.

Welcome to your exhibit!  With this you have built a full, functioning, exhibit site that contains all of your items and metadata.  If you are happy with how it all looks then congratulations!  You are done!  However if you want to make some more custom adjustments to the site, take a look at the "Theme File", "Customize", and "Finish" sections of the [official Collection Builder Documentation](https://collectionbuilder.github.io/docs/theme.html) to learn about all of the different adjustments you can make to your site.





  
**This tutorial is brought to you by the Brock University Digital Scholarship Lab.  For more information on the DSL check out our website at [www.brocku.ca/library/dsl/](https://brocku.ca/library/dsl/) or you can e-mail us at dsl@brocku.ca.**  
  
You can also find us on:  
[Facebook](https://www.facebook.com/Brock-University-Digital-Scholarship-Lab-349407235866792/)  
[Twitter](https://twitter.com/brock_dsl)  
[Instagram](https://www.instagram.com/brock_dsl/?hl=en)  
[YouTube](https://www.youtube.com/channel/UC2eEqPkDo-1N3qilxv-N_1g/featured?view_as=subscriber)










<!--- Please use reference style images so that it is easier to update pictures later --->

[imglogo]: INSERT LOGO FILENAME HERE
