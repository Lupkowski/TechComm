# Information  
This document outlines the procedure to create and host your resume using a static website/forge.  

## Requirements
- Pelican static site generator
- Python
- Github pages/git
- Resume
## Instructions  

### Installations 
**Python**  
- If your computer already has Python installed you can skip this section. You can check your system for python by opening command prompt and typing python --version
- Download [Python](https://www.python.org/)
- Follow the instuctions on the installation guide to set up Python

**Pelican Static Site Generator**
- Install Pelican by running the following command in your command prompt: python -m pip install "pelican[markdown]"

**Git**
- Download [Git](https://git-scm.com/)
- Follow the instructions on the installation guide to set up Git

  ### Repository set up
  1. Now that all the required material has been installed, we will begin creating the website.
  2. Create a [Github](https://github.com/) account
  3. In your account, create a new repository. Be sure to make the repository public to avoid permission problems down the line.
  4. Clone your repository to your local machine.
      - To clone a repository, navigate to the main page of the repo.
      - Select the green <> Code button
      - Copy the provided HTTPS link to your clipboard
      - In command prompt navigate to the folder where you would like to copy the repo. Use cd 'folder' to navigate.
      - Type git clone then paste the copied link (git clone https://copied-url-here)
      - Press Enter, now your repository is set up on your local machine.

  ### Website creation
  1. Within command prompt, navigate to the repository folder that was created in the previous step 4.
  2. Type pelican-quickstart to begin setting up your pelican project.
  3. You will be asked the following questions:
     - Where do you want to create your new web site? [.] 'Press enter, you are already in the repository folder where you want your website to be'
     - What will be the title of this web site? 'Enter your websites title (websites name)'
     - Who will be the author of this web site? 'Enter the author of the website (in most cases that is you)'
     - What will be the default language of this web site? [en] 'The default should be set to English, if you need to change it then type in the preferred default language'
     - Do you want to specify a URL prefix? e.g., https://example.com (Y/n) 'Enter Y, then enter in https://username.github.io/example where username is your github username and example is the name of your repository'
     - Do you want to enable article pagination? (Y/n) 'The default is set to yes, press Enter'
     - How many articles per page do you want? [10] 'The default is set to 10, you can customize this number to fit your preference'
     - What is your time zone? [America/Winnipeg] 'If the default is not correct, enter in the proper timezone in the format continent/city'
     - Do you want to generate a tasks.py/Makefile to automate generation and publishing? (y/N) 'The default is set to yes, press Enter'
     - Do you want to upload your website using FTP? (y/N) 'The default is set to no, press Enter'
     - Do you want to upload your website using SSH? (y/N) 'The default is set to no, press Enter'
     - Do you want to upload your website using Dropbox? (y/N) 'The default is set to no, press Enter'
     - Do you want to upload your website using S3? (y/N) 'The default is set to no, press Enter'
     - Do you want to upload your website using Rackspace Cloud Files? (y/N) 'The default is set to no, press Enter'
     - Do you want to upload your website using GitHub Pages? (y/N) 'Enter Yes as we will be using GitHub Pages'
4. Your pelican project is created

### Creating the resume  
1. Using a text editor of your choice, (Word, notepad are some examples) create your resume using Githubs markdown formatting.
2. Farther down this page, under Readings and resources are links to syntax guides for Githubs markdown formatting.
3. At the top of your resume you must include the following lines:
    - Title: 'The name of your file'
    - Author: 'The Author of your file'
4. See Resume.md under the content folder of this repository for formatting examples.
5. Upon completion, save your resume using the .md file type (ex. resume.md)

### Uploading the resume
1. Within command prompt or file explorer navigate to your repository and select the folder labeled content
2. Inside of content, create a new folder called pages and click on it.
3. Move the resume you completed in the previous section to the pages folder (Repository/content/pages/Resume.md).
4. Return to your repository folder. If you were using File explorer, open command pormpt and navigate to your repository folder.
5. Use the following commands to commit your changes from your machine, to the GitHub repository
    - git add .
    - git commit -am "Uploading resume"
6. Now that the changes have been commited, generate the sites content and push it to github pages.
   - pelican content -s publishconf.py
   - ghp-import output -b gh-pages
   - git push origin gh-pages
7. Using a browser, open GitHub and naviagte to your repository
8. Click on settings
9. Clicks on Pages on the left hand menu
10. Under the Build and Deployment, Source, select Deploy from a branch
11. Under Branch select gh-pages
12. Click save to apply these changes
13. After a few seconds at the top of that page you should see: Your site is live at https://username.github.io/repository/
14. Click on the link to view your website
     
     
## Readings and resources  
For more information on using markdown in Github see [Basic formatting](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) and [Quickstart](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/quickstart-for-writing-on-github)  
For different website themes, look into [Pelican Themes](https://docs.getpelican.com/en/latest/themes.html) for instructions on how to change the theme of your site.  
For more information on Pelican, including how to quickly preview your site using local hosting see [Pelican](https://getpelican.com/)
For more information on git's applications and features see [Git](https://github.com/git-guides)


## FAQ  
**Why is Markdown better than writing raw HTML?**  
Markdown and HTML are two common markup languages. However, Markdown is a simple, lightweight easy to learn language compared to the more complex HTML. Markdown uses a minimalistic form for syntax that resembles plain text. HTML makes use of tags to format text which can make the language harder to learn and harder to read.  

**I changed the Markdown version of my resume, so why don’t I see the changes when I refresh the website in my browser?**  
Static websites do not update automatically when a change has been made. You need to recompile your site and push the changes to your repository then redeploy your website for it to update.  
*Recompile:* pelican content -o output -s pelicanconf.py  
*Commit the changes:* ghp-import output -b gh-pages  
*Push the update to the site:* git push origin gh-pages  

## Credits  
*Left blank as I was away for the peer review exercise*
