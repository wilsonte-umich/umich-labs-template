## Template description

The **umich-labs-template** is a starting point for a research laboratory's or project's 
[GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/about-github-pages) 
web site using the [umich-labs](https://github.com/wilsonte-umich/umich-labs) Jekyll theme.

This template uses a permanent fork of the [petridish](https://github.com/peterdesmet/petridish) theme, with extensive modifications from that base but with a similar look and feel.

## Template usage

### Create a new repository from this template

**To get started quickly**, [click here to create a new repository from this template](https://github.com/wilsonte-umich/umich-labs-template/generate).

You will be prompted for the user and name of the repository you would like to create.
We recommend that you use 'USER_NAME.github.io' as the name of your repository, e.g., to create repository https://github.com/USER_NAME/USER_NAME.github.io.
That way, your web site will be available through the URL https://USER_NAME.github.io.

### Activate your web page on github.io
  
Activate your new web site for loading via github.io as follows:

- navigate to your new repository on GitHub
- click "Settings"
- click the "Pages" tab on the left
- edit the "Source" to be branch 'main' and folder '/root'
- click 'Save'
  
After a minute or two, your site will be live at the link indicated on
Settings / Pages.  It will track your repository to keep your site up
to date whenever you push or merge content changes into the 'main' branch.

### Clone your site repo locally

Clone the repository to your local computer - you will edit and pushing changes from there (see below).

### Use the umich-labs Content Management System

The easiest way to change the content of your site is to use the R Shiny-based content management system (CMS) built into your new site. 
The CMS is easily activated by:

- running either the `run_cms.bat` or `run_cms.sh` script by double-clicking it on your local computer clone
- point any web browser to http://localhost:8000/
- use the tools in the browser window, following the instructions in the web page

The first time you use the CMS you will need to wait for various R packages to be installed. 

### Manually update your web site's contents

You can also manually explore and edit all of the files within
your new repo clone. They create the contents of your web page. Briefly:
- the '_data' folder carries lists of people, publications, etc.
- the 'assets/images' folder is where you should put images
- the 'content' folder is where you write expanded pages for individual projects, posts, etc.
- the 'pages' folder is where you create the constant content for different page types

Because of the straightforward file structure, we encourage you to do
any manual editing of your website in the 
[Visual Studio Code](https://code.visualstudio.com/)
editor. The basic steps are:

- install VS Code
- [clone your site's repository](https://code.visualstudio.com/docs/editor/github)
- find the files in the file tree and edit them as you would any file
- use the Preview function to view and proofread your rendered markdown
- push your changes back to GitHub

GitHub will automatically rebuild our site whenever you push changes to it.

Even if you mainly use the CMS for site editing, you will need some method
like VS Code, or GitBash, etc., to push changes to GitHub.

### Configure your new repository's basic information

Open and edit the following files, following the instructions in the comments
regarding which specific lines you should edit to match your needs.  

As with all files that define your site, you can edit them using the CMS
or manually, whatever suits you.

- _config.yml
- _data/base/footer.yml
- _data/base/navigation.yml
- LICENSE (to add your name on the Copyright line)
- README.md (to replace these instructions, if desired)

### A few markdown basics and Jekyll support functions

Editing site content in markdown is quite easy. First, 
pages require Jekyll "front matter" as YAML content between the '---' markers
at the top of the file. README files will help you see what information is expected.

https://www.google.com/search?q=simple+yaml

```
---
title: xxx
---
```

Otherwise, page content is mostly just typed as text, with a few simple markdown tags
providing headings, links, and highlights (see template files for examples).  

https://www.markdownguide.org/basic-syntax/

```
### Heading Level 3
#### Heading Level 4

**Bold Text**
_Italic Text_

- list item 1
- list item 2

[Link Text](http://link.to.site)
![Image Text](http://path.to.image)
![Image Text]({{ assets/images/xyz.jpg | relative_url }})
```

The last example above uses Jekyll Liquid syntax to call the 'relative_url' function for an image added to the assets/images folder. In addition, the umich-labs theme provides a few other Liquid helpers. The following will include a citation as a link to a PubMed search ('search' might be text or a PMID):

```
... as shown by Wilson {% include citation.html search="xyz" %}.
```

The following will include a responsive figure panel with a border, caption and image:

```
{% include figure.html  
    image="assets/images/xyz.jpg"
    title="Figure Title"
    caption="Figure caption text."
%}
```

## License

The content of this repository and web site is subject to
[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/).
