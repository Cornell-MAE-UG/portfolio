# Portfolio Instructions

This template is the start of your professional portfolio. It is also part of your journey at MAE and will be reviewed, as needed, by your instructor and the Undergraduate Program Office.

You only need to set it up once, and then your work is a loop: **Edit** your files &rarr; **Preview** the portfolio site on your own screen &rarr; **Publish** it to the web by pushing to GitHub.

> ⚠️ **Note :** This README was copied into your repository and does not update when the template does. If something here does not match what you see, check the [original template README](https://github.com/Cornell-MAE-UG/portfolio/blob/main/README.md).

---

## Set Up Your Portfolio (do this once)

### Create Your Own Repository from the Template

1. Go to the [template repository](https://github.com/Cornell-MAE-UG/portfolio) on GitHub
    > ⚠️ You probably want to open this link in a new window to keep reading this document.
2. Click the green **Use this template** button, then **Create a new repository**.
<img src="assets/readme/use-this-template.png" width="600" />

3. Under "Owner", choose your own GitHub account.
4. Give the repository a name. Something like `portfolio` is a good choice, since the name becomes part of your published web address.
5. Leave the repository set to **Public**. On a free GitHub account, only public repositories can be published as a website, so a private one can never go live.
6. Click **Create repository**.

You now have your own repository, a full, independent copy of the template. Nothing you do to it affects the template, and nothing done to the template changes yours. Everything from here on happens in *your* repository.

### Turn On GitHub Pages

This is what puts your portfolio on the web. Do it now, before you change anything: the template is already a working site, so you will have something live to look at from the start. It happens in your repository's settings, not your account settings.

1. Open your repository's **Settings** tab.
<img src="assets/readme/settings.png" width="600" />

2. Choose **Pages** in the left sidebar. Under "Build and deployment", check that "Source" says **Deploy from a branch**, then set "Branch" to `main` and the folder to `/ (root)`.
<img src="assets/readme/pages-settings.png" width="600" />

3. Click **Save**.

After a minute or two your site is live. **Its address is shown at the top of that same Pages settings page**. Open it: what you see is the template, and the rest of these instructions are how you make it your own.

### Open a Working Copy

Your working copy will live in a [Codespace](https://github.com/features/codespaces): an online development environment where you can edit, test, commit, and push. Create one from the green "Code" button on your repository.

<img src="assets/readme/codespace-button.png" width="400" />

> 🚨 Working in a Codespace is not the same as editing directly on GitHub. The Codespace is your private test computer. This means your changes still have to be committed and pushed to GitHub before they appear online. The same goes for the preview server in Step 2: it is temporary and visible only to you, and nothing is published until you push.

#### For Advanced Users

You can, of course, clone the repository to your laptop and work in an editor like [Visual Studio Code](https://code.visualstudio.com/), or in a terminal with the git command line. You may have to sort out some Ruby setup that a Codespace handles for you, but you can work offline and previews are faster.

---

## Step 1: Make It Your Own

> Square brackets `[ ]` mark placeholders. Delete the brackets along with the text inside; do not keep them around your own words. Brackets in a link, like `[Download my CV](...)`, are not placeholders.

### Name

Change `title` and `name` in `_config.yml` to your actual name. Your name is taken from there everywhere it appears: the heading on your home page, the menu bar, and the browser tab.

### Homepage
- In `_config.yml`, replace `description` with one line about yourself. It appears under your name at the top of your home page.
- In `index.md`, replace the placeholder text with a short introduction to yourself.
- Replace `assets/images/profile-pic.jpg` with a portrait of yourself.

### Projects

Make one page per project in the `_projects` folder, using an example page (such as `2022-trig-analysis.md`) as your starting point. The example pages also show how to put code and images in a page. The filename sets the order of your gallery, so start it with the date, as the examples do.

At the top of each page, between the `---` lines, is the **front matter**. Change `title`, `description` and `technologies` to match your project. Three more settings control how it appears:

- `image` — the project's main picture. Any shape works; it is cropped to match the others.
- `imagealt` — a short description of what that picture shows, for example `imagealt: Shaded CAD rendering of a 1940s tabletop radio`. A screen reader reads this aloud, and search engines read it, in place of the picture itself.
- `featured` — your home page shows three projects: the three newest, unless you mark others with `featured: true`.

Once you have pages of your own, **delete the example pages**, and delete the pictures in `assets/images` you are not using.

> 💡 **Design Tip:** Photograph your work against a plain background, in landscape, one thing per picture. Consistent images are the biggest payoff to making a portfolio look professional.

For more advanced formatting, see the [Jekyll Markdown documentation](https://jekyllrb.com/docs/markdown/).

### CV
- Replace `assets/CV.pdf` with your own CV as a PDF.
- The example text in `_pages/cv.md` is yours to edit or delete, if you just want a PDF CV.

> ⚠️ **Privacy Notice:** Your CV becomes a public file on the web, so take out your home address and phone number before you commit it. Replacing the file later does not undo this: every version you have ever committed stays in your repository's history, where anyone can still read it.

### Colors and Styling

Set `color_scheme` in `_config.yml` to one of the schemes listed in the comment next to it:

```yaml
color_scheme: aqua
```

Beyond the schemes, you can change colors, fonts, spacing, and anything else by editing `_sass/custom.scss`. See [Advanced Customization](#advanced-customization) below.

### Save Your Work

Commit often as you work. Each commit saves your progress. In the terminal, run:

```bash
git add .
git commit -m "Add heat exchanger project"
```

The message in quotes is yours: a short description of what you changed.

> ⚠️ `git add .` stages **every** file in the folder, not only the ones you meant to edit, and anything you commit becomes public and permanent. Keep anything you do not want on the web in the `private/` folder: nothing in there is ever committed or published.

In a Codespace or VS Code, you can stage and commit through the Git panel instead: the small branch icon in the left sidebar ([documentation](https://code.visualstudio.com/docs/editor/versioncontrol)).

Committing saves your work in your repository. It does not put it on the web; that happens in Step 3.

---

## Step 2: Preview Your Site

At any point you can see your portfolio as a website, on your own screen, by running a preview server. 

> ⚠️ **Note:** You might be tempted to edit your files on GitHub directly, but that skips the testing step, and in a real work setting you would never edit code directly on a server.

Previewing your site happens **in the terminal**: the one at the bottom of your Codespace, or your own terminal on your laptop. If the Codespace terminal is closed, open one from the menu at the top left (three horizontal lines): `Terminal -> New Terminal`.

Once, to install the packages Jekyll needs. The first time, this may take a few minutes:
```bash
bundle install
```

Then, to start the server:
```bash
bundle exec jekyll serve
```

Leave the server running while you work. Most edits appear as soon as you save the file and reload the page. Changes to `_config.yml` are the exception. To pick those up, click into the terminal and press ctrl-c to stop the server, then run the command again.

The server prints the address of your site:
```text
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.
```

Cmd-click (Mac) or Ctrl-click (Windows) that address **in the terminal** to open it. Do not just type the address into your browser. It will not work in a Codespace.

---

## Step 3: Publishing Your Portfolio to the Web

Your portfolio does not change on the web until you push your commits to GitHub. The preview server in Step 2 is temporary, and nobody else can see it.

### Push Your Changes to GitHub

Once everything looks good, commit anything outstanding (Step 1), then push:

```bash
git push
```

Committing saves your work in your repository. Pushing sends it to GitHub, which rebuilds your live site.

In a Codespace or VS Code, the Git panel can push for you.

### Your Published Portfolio Site

A few minutes after each push, your changes are live. Your address is built from your GitHub username and the repository's name, so if you rename the repository or move it to another account, the old address stops working and Settings → Pages shows you the new one. Remember to update your résumé and profiles if you have already put the link there. :tada:

**You can now replace this README with something of your own**, but have a look at the sections below first.

### Taking Your Portfolio Offline

To take your site off the web, go to Settings → Pages and use **Unpublish site**. That removes the public website only: your repository stays exactly as it is, and you can publish again later by setting the branch the same way you did at setup.

---

## If Something Goes Wrong

**My site's address gives a 404, or says "There isn't a GitHub Pages site here".**
Pages was never turned on. Go to your repository's Settings (not your account settings) → Pages, set Source to "Deploy from a branch", Branch to `main` and the folder to `/ (root)`, and save. If there is no branch to choose, or the option is missing, check that your repository is **Public**. On a free account, only public repositories can be published.

**I pushed my changes but the website never updated.**
Give it a few minutes and hard-refresh your browser (Cmd-Shift-R or Ctrl-Shift-R). If it is still stale, the build **failed**. GitHub leaves the old version up and says nothing on the site itself. Open your repository's **Actions** tab, look for a red ✗ next to "pages build and deployment", and click it to read the error.

**I edited `_sass/custom.scss` and now the site will not update at all.**
An error in that file stops the whole build, so nothing publishes. Look for a missing `}` or `;`, or a `$variable` spelled differently from where it was defined. To get back to a working site, undo your last change to that file, commit, and push.

**I renamed my repository and now the site looks like plain text with no pictures.**
Your web address changed with the name, and the published site catches up on its next build. Push any commit to trigger one. The current address is always the one shown in Settings → Pages.

**I came back to my Codespace and my changes are gone.**
Codespaces shut down when idle and are deleted after longer inactivity, taking anything you never committed with them. Commit often, and push before you stop working for the week.

**I cannot create a Codespace. It says I have used up my included hours.**
Codespaces are free up to a monthly limit on your personal account, and that limit resets each month. Delete any codespaces you are no longer using from [github.com/codespaces](https://github.com/codespaces), and stop yours when you finish working rather than leaving it running. You can also raise the limit, for free, by activating the [GitHub Student Developer Pack](https://education.github.com/pack), worth doing regardless. If you are stuck in the meantime, you can work on your own laptop instead: see "For Advanced Users" in the setup section.

**The address the server prints, `http://127.0.0.1:4000/`, will not open.**
`127.0.0.1` means "this computer", and the Codespace is not your computer, so copying that address into your own browser will never work. Click the link *in the Codespace terminal*, or open the "Ports" tab at the bottom and use the entry for port 4000.

---

## Advanced Customization

You can restyle any part of the portfolio by editing `_sass/custom.scss`, which is written in [Sass](https://sass-lang.com/), a superset of CSS, so ordinary CSS rules work there as they are. For example, change the width of the text by setting the `max-width` of `.container`:

```css
.container {
  max-width: 1000px;
}
```

Underneath, your portfolio is a [Jekyll](https://jekyllrb.com/) site, [documented here](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll). That means you can go further and replace the styling with another Jekyll theme, from [Jekyll Themes on GitHub](https://github.com/topics/jekyll-theme), [Start Bootstrap](https://startbootstrap.com/themes/jekyll/), or [Jekyll Themes](https://jekyllthemes.io/). Follow the theme's own instructions, and expect to adapt your content to fit it.

## Tips and Tricks

### Commenting Out Content

To keep a bit of text or an image in a page without showing it, wrap it in a `{% comment %}` block:

```liquid
{% comment %}
    Stuff you want to comment out.
{% endcomment %}
```

> This hides the text from the published page only. It is still in the file, in your public repository, and in that repository's history. An HTML comment (`<!-- ... -->`) hides even less: it is sent to the browser, and anyone can read it with View Source.
