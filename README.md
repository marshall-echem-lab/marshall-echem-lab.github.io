# Marshall Echem lab page

This is repository for [Marshall Echem lab](http://marshall-echem-lab.github.io/). We use Jekyll to run our Github page.

## Editing the lab website

Below, we explain how to edit the lab webpage

### Add posts

It's very easy to add a post. All the posts are located in `_posts` folder. It arrangement is based on date. Each post can be written in markdown format. You just have to state headers before writing: `title`, `description` and `categories`. See the following headers:

``` markdown
---
title: How do potentiostats work ?
description: potentiostats are the major critical instruments in our lab 
categories: [methods, hardware, teaching]
date: YYYY-MM-DD
---
```

We have 4 categories: `methods`, `hardware`, `research`, `teaching` you can choose and this will be rendered to different location.

### How to add posts

- **Write and save in the website onedrive**, under the `_posts` folder. You need to use markdown and save with the following format `2016-02-03-post-name.md`. These get committed and pushed to the GitHub repo. 


Once pushed to the repo, it takes approximately a minute for the GitHub page to be generated.

### Add yourself

You can add yourself to the page in `_people` folder just create file name `<firstname>_<lastname>.md` in the folder. We require few line of header before you start writing your own page. See the following for the header

``` markdown
---
name: Firstname Surname
position: postdoc
avatar: yourphoto.jpg <!-- `stored in images/people` folder -->
joined: 2014
project: <!-- short title of your work -->
completed: <!-- if alumni, when did you leave ? -->
now: <!-- if alumni, where are you now ?-->
---
```

If you don't have information, just leave it blank. The avatar will bring photo from `images/people` folder and display it on people page. 
For lab position, you can choose position from a few classes including `postdoc`, `postgrad`, `visitor`, `alumni`. Position will put you into section that you choose.

### Add new publications

All publications from the lab are uploaded in bibtex format. We then have a script which generates a list in markdown `publications.md`. A *.docx file is also generated for Aaron's use.

### Add news

All news presented in the front page by editing `_data/news.yml`. There are some symbol that cannot be used directly e.g. `:`, be careful

## Internal

### When to Add/Remove Yourself from the Webpage

**When to ADD yourself:**
- When you officially join the Kording Lab as a graduate student, postdoc, research staff, or visiting scholar
- Ideally within your first week of joining the lab
- After confirming with Konrad or the lab manager that you are officially part of the lab

**When to REMOVE yourself:**
- When you graduate or complete your position in the lab
- When transitioning to alumni status (you don't delete your profile, just change your position to 'alumni')
- If you're a visiting scholar, when your visit period ends

### How to Add Yourself to the People Page

1. **Create your profile file:**
   - Navigate to the `_people` folder
   - Create a new file named `<firstname>_<lastname>.md` (all lowercase, e.g., `john_smith.md`)
   
2. **Add the required header:**
   ```markdown
   ---
   name: Your Full Name
   position: [choose one: gradstudent/postdoc/researchstaff/visiting/alumni]
   avatar: yourphoto.jpg
   joined: 2024
   ---
   ```
   
3. **Add your photo:**
   - Add a professional photo to the `images/people/` folder
   - Name it to match the avatar field in your header (e.g., `yourphoto.jpg`)
   - Recommended: square aspect ratio, at least 400x400 pixels
   
4. **Write your bio:**
   - After the header, write a brief bio (2-3 paragraphs)
   - Include your research interests, background, and current projects
   - You can use markdown formatting for links, bold text, etc.

5. **Submit your changes:**
   - If comfortable with git: commit and push your changes, then create a pull request
   - If not: email your files to the lab manager or ask for help

### How to Update Your Profile

1. **Edit your existing file** in `_people/<firstname>_<lastname>.md`
2. **Update any information** that has changed
3. **Update your photo** if needed (replace the file in `images/people/`)
4. **Commit and push** your changes or ask for help

### How to Transition to Alumni Status

When leaving the lab:

1. **Edit your profile file** in `_people/<firstname>_<lastname>.md`
2. **Change the position field** from your current position to `alumni`:
   ```markdown
   position: alumni
   ```
3. **Add a line about where you're going** in your bio (e.g., "Now at [Company/University]")
4. **Keep your profile** - don't delete it! Alumni remain part of the lab community
5. **Commit and push** the changes

### Getting Help

- If you're not familiar with Git/GitHub, ask or help
- You can also edit directly on GitHub.com through the web interface




