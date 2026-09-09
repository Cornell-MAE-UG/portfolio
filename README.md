# Portfolio Instructions

This is a template for you to start building your professional portfolio. It is also part of your journey at MAE and will be reviewed, as needed, by your instructor and the Undergraduate Program Office.

This README travels into your own copy of the template. Step 1 below shows you how to make that copy, and the steps after it show you how to edit, test, and publish your portfolio. Once you are up and running, you can delete this README file or replace it with your own content.

> ⚠️ Because this README was copied into your repository, it does not update when the template does. If something here does not match what you see, check the [original README](https://github.com/Cornell-MAE-UG/portfolio/blob/main/README.md) for the current instructions.

## Portfolio Editing Workflow

Before the details, here is the shape of the whole process:

1. **Once:** create your own copy of the portfolio repository, and open a working copy of it that you can edit (Step 1).
2. **Edit** the files in your working copy — text, images, new project pages — and [commit](https://docs.github.com/en/get-started/using-git/about-git#basic-git-commands) often to save your progress (Step 2).
3. **Test** your changes on a local web server, which only you can see (Step 3).
4. **Publish** by pushing your commits to GitHub, which updates your live site within a few minutes (Step 4).

Then repeat from 2. Your portfolio is stored on GitHub and you _could_ edit it there directly, but that skips the testing step — and in a real work setting you would never edit code directly on a server.

---

## Step 1: Creating Your Portfolio Repository and a Working Copy

### Create Your Own Repository from the Template

Your portfolio starts as your own copy of this template repository, stored in your personal GitHub account.

1. Go to the [template repository](https://github.com/Cornell-MAE-UG/portfolio) on GitHub.
2. Click the green **Use this template** button, then **Create a new repository**.
3. Under "Owner", choose your own GitHub account.
4. Give the repository a name. Something like `portfolio` is a good choice, since this name becomes part of your published web address.
5. Click **Create repository**.

You now have your own repository. It is a full, independent copy: nothing you do to it affects the template, and nothing done to the template changes yours. Everything from here on happens in *your* repository, not in the template.

### Open a Working Copy

Your working copy will live in a [Codespace](https://github.com/features/codespaces): an online development environment where you can edit, test, commit, and push your work. Create one from the green "Code" button on your repository, as shown below.

<img src="assets/readme/codespace-button.png" width="400" />

Editing and committing in a Codespace is not the same as editing directly on GitHub. Changes you make there still have to be committed and pushed to GitHub before they appear online. The same goes for the test server you will run in Step 3: it is temporary and visible only to you, and nothing is published until you push.

#### For Advanced Users

You can instead clone the repository to your own laptop and work in an editor like [Visual Studio Code](https://code.visualstudio.com/), using it to edit, commit, and test. You may have to sort out some setup that a Codespace handles for you, but you can then work offline, and edits and previews are faster.

If you are comfortable in a terminal, you can also use the git command line interface (CLI) and any editor you like.

Please refer to the [Jekyll](https://jekyllrb.com/) and [GitHub Pages](https://pages.github.com/) documentation for more advanced usage.

---

## Step 2: Editing the Files to Personalize Your Portfolio

Start with these basic edits to make the portfolio yours.
> The `< >` brackets mark placeholders. Delete them along with the text inside; do not keep them around your own text.

### Name

Change every reference to `Your Name` or `<Your Name>` to your actual name, in these files:
- `_config.yml`
- `index.md`
- `_pages/projects.md`
- `_pages/cv.md`

### Homepage
- In `index.md`, replace the placeholder text with a short introduction to yourself.
- Replace the placeholder image `assets/images/profile-pic.jpg` with a portrait of yourself.

### Projects
- In the `_projects` folder, make one page per project. Use the example pages (such as `2022-trig-analysis.md`) as your starting point.
- Each project has a main, square image, set by the `image` variable in the front matter — the block at the top of the page between the `---` lines.
- Right next to it, set `imagealt` to a short description of what that image shows, for example `imagealt: Shaded CAD rendering of a 1940s tabletop radio`. A screen reader reads this aloud, and search engines read it, in place of the picture itself. The example pages show the format.
- Portfolio images live in `assets/images`. Delete the ones you don't need. (The screenshots used by this README live separately, in `assets/readme`.)
- The filename sets the order of the projects in your gallery, so start it with the date, as the examples do. Any numbering scheme works if you would rather order them another way.
- The example pages also show you how to include code and images in the body of a project page.
- For other formatting, see the [Jekyll Markdown documentation](https://jekyllrb.com/docs/markdown/).
- Delete the example project pages once you have your own.

### CV
- Replace the placeholder `assets/CV.pdf` with your own CV as a PDF.
- The placeholder text in `_pages/cv.md` is yours to edit or delete, as you prefer.

> ⚠️ Your CV becomes a public file on the web, so take out your home address and phone number before you commit it. Replacing the file later does not undo this: every version you have ever committed stays in your repository's history, where anyone can still read it.

### Color Schemes

The template comes with several color schemes. To choose one:

1. Open `_config.yml`.
2. Find the `color_scheme` setting.
3. Change its value to the scheme you want. The comment next to it in `_config.yml` lists the available names.

For example:
```yaml
color_scheme: aqua
```

### Other Styling

Beyond the schemes, you can change colors, fonts, spacing, and anything else by editing `_sass/custom.scss`. See [Advanced Customization](#advanced-customization-using-other-jekyll-themes) below for what is possible there.

### Commit Your Changes

Commit often as you work — each commit saves your progress. In the terminal, run:

```bash
git add .
git commit -m "<Commit Message>"
```

Replace `<Commit Message>` with a short description of what you changed, for example `Add heat exchanger project`.

> ⚠️ `git add .` stages **every** file in the folder, not only the ones you meant to edit, and anything you commit becomes public and permanent. Keep graded feedback, drafts, and anything else you do not want on the web in the `private/` folder: nothing in there is ever committed or published.

In VS Code or a Codespace, you can stage and commit through the Git panel instead — the small branch icon in the left sidebar. Its usage is documented [here](https://code.visualstudio.com/docs/editor/versioncontrol).

---

## Step 3: Running the Site Locally for Testing

At any point, you can see your portfolio as a website by running a local web server. This happens **in the terminal** — the one at the bottom of your Codespace, or your own terminal if you are working on your laptop.

If the Codespace terminal is closed or hidden, open a new one from the menu at the top left (three horizontal lines): `Terminal -> New Terminal`.

### Install Packages (Once)

Run this once, before the first time you start the server, to install the packages Jekyll needs:
```bash
bundle install
```

### Running the Local Portfolio Server

Then start the server:
```bash
bundle exec jekyll serve
```

Leave it running while you work. Most edits are picked up automatically — save the file and reload the page. Changes to `_config.yml` are the exception: click into the terminal, hold the Control key and press C to stop the server, then run the same command again. This is what "press ctrl-c" means anywhere in the terminal, and it is typed, not clicked.

The server prints the address of your site:
```text
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.
```

Cmd-click (Mac) or Ctrl-click (Windows) that address to open it in a new browser tab. Click it **in the terminal**: in a Codespace, copying the address into your own browser will not work, because `127.0.0.1` means "this computer" and the Codespace is not your computer. On your laptop, `http://localhost:4000/` works in any browser.

---

## Step 4: Publishing Your Portfolio to the Web

Your portfolio is not live on the web until you push your changes to GitHub and turn on GitHub Pages. What you see on your local test server is not permanent and nobody else can see it.

### Push Your Changes to GitHub

Once everything looks good, commit anything outstanding and push. By this point you will usually have committed several times already.

```bash
git add .
git commit -m "<Commit Message>"
git push origin main
```

> Remember that `git add .` stages everything in the folder. Anything private belongs in `private/`.

In VS Code or a Codespace, the Git panel can stage, commit, and push for you.

### Set Up GitHub Pages

You only have to do this once, and only in **your repository's** Settings — not your account settings.

1. Open your repository's **Settings** tab.
<img src="assets/readme/settings.png" width="600" />

2. Choose **Pages** in the left sidebar. Under "Build and deployment", check that "Source" says **Deploy from a branch**, then set "Branch" to `main` and the folder to `/ (root)`.
<img src="assets/readme/pages-settings.png" width="600" />

3. Click **Save**.

### Your Published Portfolio Site

After a few minutes, your portfolio will be live. **Its address is shown at the top of that same Pages settings page** — that is always the correct one.

The address is built from your GitHub username and the repository's name. If you ever rename the repository or move it to another account, the old address stops working and the Pages page will show you the new one. If you have already put your portfolio link on a résumé or a profile somewhere, remember to update it there too.

:tada:

**You can now replace this README with something of your own**, but have a look at the tips below first.

### Taking Your Portfolio Offline

If you ever want to take your site off the web, go to Settings → Pages and use the **Unpublish site** option. That removes the public website only: your repository and everything in it stay exactly as they are, and you can publish again later by setting the branch as above.

---

## If Something Goes Wrong

**My site's address gives a 404, or says "There isn't a GitHub Pages site here".**
Pages was never turned on. Go to your repository's Settings (the repository's own Settings tab, not your account settings), then Pages, set Source to "Deploy from a branch", Branch to `main` and the folder to `/ (root)`, and save.

**I pushed my changes but the website never updated.**
First give it a few minutes and hard-refresh your browser (Cmd-Shift-R or Ctrl-Shift-R). If it is still stale, the build **failed** — GitHub leaves the old version up and says nothing on the site itself. Open your repository's **Actions** tab, look for a red ✗ next to "pages build and deployment", and click it to read the error.

**I edited `_sass/custom.scss` and now the site will not update at all.**
An error in that file stops the whole build, so nothing publishes. Look for a missing `}` or `;`, or a `$variable` spelled differently from where it was defined. To get back to a working site, undo your last change to that file, commit, and push.

**I renamed my repository and now the site looks like plain text with no pictures.**
Your web address changed with the name, and the published site catches up on its next build. Push any commit — or make a small edit on GitHub — to trigger one. The current address is always the one shown in Settings → Pages.

**I came back to my Codespace and my changes are gone.**
Codespaces shut down when idle and are deleted after a longer period of inactivity, taking anything you never committed with them. Commit often, and push before you stop working for the week.

**The address the server prints, `http://127.0.0.1:4000/`, will not open.**
`127.0.0.1` means "this computer", and the Codespace is not your computer. Click the link *in the Codespace terminal* and it will be forwarded to you, or open the "Ports" tab at the bottom and use the entry for port 4000. Copying that address into your own browser will never work.

---

## Advanced Customization: Using Other Jekyll Themes

You can restyle any part of the portfolio by editing `_sass/custom.scss`, which is written in [Sass](https://sass-lang.com/) — a superset of CSS, so ordinary CSS rules work there as they are.

Underneath, your portfolio is a [Jekyll](https://jekyllrb.com/) site, which is documented [here](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll).

That also means you can go further and replace the styling with another Jekyll theme. Some good places to find one:

- [Jekyll Themes on GitHub](https://github.com/topics/jekyll-theme)
- [Start Bootstrap](https://startbootstrap.com/themes/jekyll/)
- [Jekyll Themes](https://jekyllthemes.io/)

Follow the theme's own installation and customization instructions, and expect to adapt your content to fit it.

## Tips and Tricks

### Commenting Out Content

To keep a bit of text or an image in a page without showing it, wrap it in a `{% comment %}` block:

```liquid
{% comment %}
    Stuff you want to comment out.
{% endcomment %}
```

> This hides the text from the published page only. It is still in the file, in your public repository, and in that repository's history. An HTML comment (`<!-- ... -->`) hides even less: it is sent to the browser, and anyone can read it with View Source.

### Changing the Text Width

In `_sass/custom.scss`, change the `max-width` of `.container`:

```css
.container {
  max-width: 1000px;
}
```
