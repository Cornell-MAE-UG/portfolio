# Portfolio Instructions

> [!WARNING]  This README file might be out of date with the latest instructions. Please refer to the [Original Repository README file](https://github.com/Cornell-MAE-UG/portfolio/blob/main/README.md) for up-to-date instructions.

This is a template for you to start building your professional portfolio. It is also part of your journey at MAE and will be reviewed, as needed, by your instructor and the Undergraduate Program Office.

Note that you are looking at your personal copy of the portfolio template repository. It was created automatically when you accepted the Assignment through the GitHub Classroom link you were provided. Once you are up and running, you can delete this README file and replace it with your own content if you wish. 

In the following sections, you will find instructions on how to edit, test, and publish your portfolio.

## Portfolio Editing Workflow

It's important to understand the logic of the workflow to edit and publish your portfolio. The process goes as follows:

1. **Create a working copy** of your portfolio, either in an online "Codespace" or on your local machine. 
Your portfolio is currently stored on GitHub. You _could_ edit it directly on there, but this is inconvenient, inefficient, and error-prone. 
> In a realistic work setting, you would never edit code directly on a server.
2. On you working copy, you **edit any relevant files**, add images, new project pages, text, etc. 
Remember to [commit](https://docs.github.com/en/get-started/using-git/about-git#basic-git-commands) often to save your progress. 
3. Test out your portfolio by **running a local test server** and see if it looks as planned.
4. If you're happy, make sure everything is committed and **push your changes to Github**. Then publish your portfolio through GitHub Pages.
> Every time you push new changes, this will initiate a process by which GitHub publish your updated portfolio on the Internet. **Make sure you understand** what edits are local to your working copy and which are pushed (sent to) the central repository on GitHub and thus public.
5. Rinse and repeat from Step 2 above. 

We will go through each of these steps in the following sections. 

---

## Step 1: Creating a Working Copy

You will set up your local copy on an online [Codespaces](https://github.com/features/codespaces) environment for development. You create a Codespace through the "Code" button as shown in the image below. This starts an online server with a development environment that enables you to edit, test, commit, and push your work.

<img src="assets/images/codespace-button.png" width="400" />

Note that editing, saving, and committing on Codespaces is not the same as editing directly on GitHub. When you make changes on Codespaces, you still need to commit and push your changes to GitHub to publish them online. Also, when you run a test server on Codespaces, it is running a temporary server that you can use to debug, but it is not considered "published" until you push your changes to GitHub.

### For Advanced Users

For more efficient operation, you can clone the code to your own laptop using a tool like [Visual Studio Code](https://code.visualstudio.com/) for editing, committing, and git commands. You might need to work around some configuration issues which are automatically solved on the Codespace machine, but the upside is that you can work offline and do changes and preview them faster.

If you have experience with command lines on terminals, you can also use the git command line interface (CLI) to maintain your local copy and use whatever editor you want to edit your portfolio.

Please refer to the [Jekyll](https://jekyllrb.com/) and [GitHub Pages](https://pages.github.com/) documentation for more advanced usage.

---

## Step 2: Editing the Files to Personalize Your Portfolio


Let's get you up and running with some basic edits to personalize your portfolio.
> No need to keep the `< >` brackets. They are just there to indicate placeholders.

### Name

Change references to `<Your Name>` to your actual name in the following files:
- `_config.yml`
- `index.md`
- `projects.md`
- `cv.md`


### Homepage
- `index.md`: Replace the placeholder text with a welcome or pitch paragraph about yourself.
- `assets/images/profile-pic.jpg`: Replace the placeholder with a portrait of yourself.

### Projects
- In the `_projects` folder: Use the provided example pages (e.g., `2022-trig-analysis.md`) to build one page per project.
- Each project has a main (square) project image, set in the page's top matter by the `image` variable in the preamble on the top of the page (the part between the `---` lines).
- All images are in `assets/images`. Delete the ones you don't need.
- It is useful to name the page with a leading date. This will determine the order of projects on your main portfolio gallery. You can also develop another ordering by naming the projects with some numerical prefix.
- The example project pages show you how to include code and images in the portfolio page.
- Refer to the [Jekyll Markdown documentation](https://jekyllrb.com/docs/markdown/) for other formatting tips.
- Delete the example project pages when you are done.

### CV
- `assets/CV.pdf`: Replace this placeholder with your own PDF CV.
- You can either edit or delete the placeholder CV markdown text. This is up to you

### Color Schemes

The provided template comes with multiple color schemes. To choose a scheme:

1. Open the `_config.yml` file.
2. Look for the `color_scheme` setting.
3. Change the value to the desired skin name. Refer to the inline comment in `_config.yml` for available skin options.


Example:
```yaml
skin: aqua
```

---

## Step 3: Running the Site Locally for Testing

Once you made your changes, or at any time you wish to, you can test your changes by running a local web server, using the `bundle` command. All of this happens **in the terminal** on Codespaces, or, for advanced users in VS Code or directly in your terminal app.

Open the terminal in your codespace by going to the top menu and selecting `Terminal -> New Terminal`.

### Install Packages (once)

You only need to run this command the first time you try to run jekyll, to install the relevant packages: 
```bash
bundle install
```

### Running the Local Portfolio Server
Then, to run the server you run the `jekyll serve` command:
```bash
bundle exec jekyll serve
```

Note that many updates to your code are automatically reloaded into the web server. However, some changes, notably to `_config.yml` require a restart of the jekyll server.

You can access the site at the URL shown by the `serve` command. It looks something like this:
```python
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.
```

---

## Step 4: Publishing your Portfolio to the Web

### Push your Changes to GitHub

Once everything looks good, commit and push your changes. In the terminal, run the following commands. Ideally, you would have added and committed many times locally before pushing to Github.

```bash
git add .
git commit -m "<Commit Edit>"
git push origin main
```

In VS Code or Codespaces, you can use the Git interface inside the development environment to stage (add), commit, and push your changes.

### Set Up GitHub Pages

Finally, for publishing your portfolio, follow these steps:

1. In your `_config.yml` file, set the `baseurl` to your portfolio repo name (e.g., `"/fa26-portfolio-hoffman/"`)


1. Go to your repository's Settings
<img src="assets/images/settings.png" width="600" />

3. Choose the "Pages" tab under "Build and Deployment", verify that "Source" says "Deploy from a branch" and under "Branch" choose `main` and `/ (root)`
<img src="assets/images/pages-settings.png" width="600" />

4. Don't forget to save this setting at the bottom of the page.

### Your Published Portfolio Site
Your portfolio should be live at `https://cornell-mae-ug.github.io/<your-repo>/`, where `your-repo` is this repository's name, probably `portfolio-<your-github-username>`. This URL is also shown in your Pages setting tab.

:tada:

**You can now replace this template README file with a more informative text**, but check out additional tips and tricks below.

### More Control over Publishing

If you add plugins and add-ons, you might need to publish using your own Gemfile, and other custom actions. See the following link to learn everything about [publishing a Jekyll site with Github Pages](https://jekyllrb.com/docs/continuous-integration/github-actions/).

---

## Advanced Customization: Using Other Jekyll Themes

You can change the style of any component of the portfolio editing the `custom.scss` file, which is written in the [Sass](https://sass-lang.com/) language.

In addition, as mentioned, your portfolio uses [Jekyll](https://jekyllrb.com/) underneath the hood. For more advanced styling of your portfolio, check out [this documentation](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll).

This also means that you can customize your portfolio to a greater extent by using other Jekyll themes. Here are some good places to find themes:

- [Jekyll Themes on GitHub](https://github.com/topics/jekyll-theme)
- [Start Bootstrap](https://startbootstrap.com/themes/jekyll/)
- [Jekyll Themes](https://jekyllthemes.io/)

Follow the theme's installation and customization instructions as needed to fit your portfolio content.

## Tips and Tricks

### Commenting Out Content

You can comment out a bit of text or an image by using the `{% comment %}` command:

```ruby
{% comment %}
    Stuff you want to comment out.
{% endcomment %}
```

### Changing the text width

Change any styling by editing the `custom.scss` file, a Sass file, which is a superset of CSS.

For example, change the text width by changing the `max-width` of `.container`:

```css
.container {
  max-width: 1000px;
}
```
