# site-source: The Github Repository for the contents of https://ncfpbl.github.io/

## General Overview

1. This site is constructed using a two-directory system using the Hugo Academic theme. Both should be cloned from GitHub and reside on your device. Materials should be manually pushed to the `site-source` repository. To publish to the actual site, use the `update.sh` file to automatically stage, commit and push to the `ncfpbl.github.io` repository. DO NOT TOUCH the contents of the `ncfpbl.github.io` repository[^caveats]
2. Before jumping into the edits, consult and familiarize yourself with the Hugo Academic theme documentation: https://sourcethemes.com/academic/
3. Academic is constantly being upgraded and the documentation is available on the site. If, in the future, the site wants an upgrade to a newer version with better features, consult Academic on best practices. *This process can get messy and you are probably better off backing up this repository into a local folder and importing the new layouts/features using a completely new site from `blogdown` and copy/paste your content from your old site. This depends on how long you wait for a new site.[^update]* 
4. If you ever mess up, FEAR NOT! A blank template of everything is in the `themes/exampleSite/` folder. It helps to consult some of the tips in there for how to use each of the functions/widgets that the site has
5. The website works on a folder system within subfolders, especially for the `content/` folder. To create pages of anything (papers, presentations, blog posts, courses), there must be a folder (named as desired to reflect the contents) and an `index.md` that contains information like titles, authors, abstracts, and other links. This is because the backend reads the `YAML` in the `index.md` file that must be included in the subfolder when building the website. Consult existing folders, sample materials under `themes/hugo-academic/exampleSite/`, and the Academic website for samples on how to do this for each type.

## Where is Everything?

*Good Question... I always ask myself this every time I edit this site...*

`config/`  
|---`languages.toml` -- If you want something other than English  
|---`menus.toml` -- Menu Bar -- use to edit menu appearances 
|---`params.toml` -- Site Parameters --mostly set but can edit as desired to change colors, fonts and contact information

`build-site.R` -- Code from `update.sh` -- a soft DO NOT TOUCH

`config.toml` -- Site configuration -- a touch only if you need to: establishes the title and URL of the site.

`resources/` -- Backend stuff for site -- a DO NOT TOUCH (you shouldn't need to touch it anyway)

`static/` -- Place for external files -- a DO NOT TOUCH EXCEPT the `img` folder and whatever other folders YOU create.  

1. Academic recognizes folders. If you create a folder of something in the `content/` folder, create one with the same name in the `static/` file to put in all non-featured images and files.
2. Use the `files/` folder for lone PDF files that are not necessarily associated with a paper. This can include CVs, letters, or other documents that is nice to show but not part of a project.

`themes/` -- site theme -- a DO NOT TOUCH (as in edit -- highly recommend reading through, especially the `exampleSite/` folder for blank templates) unless you want to upgrade. In that case, clone https://github.com/gcushen/hugo-academic.git and replace the existing `hugo-academic/` folder. As mentioned above -- THIS CAN GET MESSY!

`update.sh` -- Publish site -- Edit commit messages as desired

`assets/` -- If you want to write your own code for the backend, here is where it goes. Also houses the browser icon under `images/`

`content/` -- THE BULK OF IT ALL  

- 	`authors/` -- site authors -- creates author bios for each person. `admin/` is Jack Reilly. Everyone else has a folder with their first name and last initial. USE the FOLDER NAME as the profile ID in the publications/papers to reference someone.
-  `home/` -- home page -- More details below.
-  `publication/` -- all papers -- All papers have a shortened folder name to reference what the paper is about. USE the `categories` subfield on the `index.md` `YAML` to place labels of the paper type. This is how the papers get categorized under the pages in the "Research Approaches" broad categories section. The ones currently in use are:
	- "Mapping Florida Politics"
	- "Voting in Florida"
	- "Rural and Place Based Politics"
	- "Social Networks"
- `join/` -- Information on Joining the Lab
- `post/` -- Site blog feature -- currently muted[^mute]
- `slides/` -- Academic Markdown slides feature -- currently muted
- `courses/` -- online course feature -- currently muted
- `talk/` -- presentations feature -- currently muted
- `project/` -- portfolio feature -- currently muted
- You can create new folders in the `content/` folder to create new content pages or sections on the home page. It must come with an `index.md`. For example, I created the `join/` folder for the "Join Us" page.

`content/home/` -- Because there is so much in this folder, it gets it's own section

*There is a lot in the Home folder. This is where Academic showcases all of the widgets and provides examples of everything you can do. The best way to really learn everything is by poking around*

- `top.md` -- the NCF picture and intro blurb
- `approaches.md` -- Lab project categories
- `people.md` -- structure of the "Meet the Team" section
- `publications.md` -- organizes presentation of papers
- `index.md` -- backend command structure for home page -- a DO NOT TOUCH
- `contact.md` -- contact widget. Contact information is edited in the `params.toml`
- Everything else is muted[^show]
- You can also add to this by creating new `.md` files and specifying the widget and parameters using existing ones as examples.

## Odds and Ends

To create the site, I general folder in my desktop (you can name it whatever you want) to contain 4 things

- `site-source`: the version that I am editing
- `ncfpbl.github.io`: Published site -- in order for the system to work, both need to be cloned locally
- `sample`: A blank folder where I include some templates extracted from `themes/hugo-academic/exampleSite/` for easy reference
- `sorted-papers/`: A folder where I contain a copy of the papers under `site-source/content/publication/` in sorted sub-folders so I know what paper belongs in which category. 

There are a few things I learned from making this site, which I document in my running list of things here: https://lin-jennifer.github.io/post/websites-using-academic/

This is a lot to learn at first. I highly recommend a designated person working on the site and having everyone request edits to their papers as desired. Alternatively, the site can sit on one of the lab computers and all edits can be made there.


[^caveats]: Only touch the `ncfpbl.github.io` repository if you need to clean out files that are deleted in the `site source` but do not delete automatically in the `ncfpbl.github.io` backend. Sometimes, this can affect the build process. This process is best described here: https://alison.rbind.io/post/2019-03-04-hugo-troubleshooting/  
[^mute]: Features can be unmuted by adding stuff to them and activating them either in the `home/` page or by creating a menu option to access them as a separate page from home.  
[^show]: To activate a widget on the home page, use `active=` on the file's `YAML` and change the settings according to the comments (true/false).  
[^update]: Alternatively, you can star the Academic GitHub (https://github.com/gcushen/hugo-academic) to monitor when changes are happening and update `themes/hugo-academic/` with each posted change on the Updates page in the documentation (https://sourcethemes.com/academic/updates/v4.9.0/)

# Breaking Changes

- Use `i18n/en.yaml` to edit reformatted text under each ID. **EDIT the text next to "Translation" ONLY** 
- For Example talks and publications are edited such that SEE ALL talks and publications are now SEE ALL PRESENTATIONS and SEE ALL PAPERS respectively:

```
- id: more_talks
  translation: See all presentations

- id: more_publications
  translation: See all papers
```

- When updating, check to make sure that this file has not been changed in `theme/hugo-academic/` -- a good way to check can be using `git status` when a new `hugo-academic/` theme file has been added.