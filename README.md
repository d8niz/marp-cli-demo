# Marp CLI example

[![Open in Visual Studio Code](https://open.vscode.dev/badges/open-in-vscode.svg)](https://open.vscode.dev/yhatt/marp-cli-example)

**The good starter example for using [Marp] via [Marp CLI].**

- Write your slide deck by [Marp] Markdown.
- Manage the content of slides via Git. (Using [GitPitch](https://github.com/gitpitch/gitpitch) style `PITCHME.md`)
- Host your deck at GitHub, and publish as webpage with [GitHub Pages], [Netlify], and [Vercel].
- Blazingly fast delivery out of the box. [Acquired all 100% Lighthouse scores!](#lighthouse)

[marp]: https://marp.app/
[marp cli]: https://github.com/marp-team/marp-cli
[github pages]: https://pages.github.com/
[netlify]: https://www.netlify.com/
[vercel]: https://vercel.com/

<p align="center">
  <a href="https://yhatt.github.io/marp-cli-example"><img src="https://yhatt.github.io/marp-cli-example/og-image.jpg" width="500" /></a>
</p>

## See published slide deck

- <img src="https://icongr.am/octicons/mark-github.svg" width="24" height="24" valign="bottom" /> **[GitHub Pages]**: https://yhatt.github.io/marp-cli-example
- <img src="https://icongr.am/simple/netlify.svg?colored" width="24" height="24" valign="bottom" /> **[Netlify]**: https://yhatt-marp-cli-example.netlify.app/
- <img src="https://icongr.am/simple/zeit.svg" width="24" height="24" valign="bottom" /> **[Vercel]**: https://marp-cli-example.yhatt.vercel.app/

### Lighthouse

<p align="center">
  <img src="https://user-images.githubusercontent.com/3993388/115988866-7cd7fe00-a5f6-11eb-9e51-7a62da998eca.png" width="615" alt="Acquired all 100% Lighthouse scores" />
</p>

## Usage

It's surprisingly easy to start publishing your slide deck!

### <img src="https://icongr.am/octicons/mark-github.svg" width="24" height="24" valign="bottom" /> [GitHub Pages]

Create a new _public_ repository based on this repository, from **"Use this template"** button!

[![](https://img.shields.io/badge/-Use%20this%20template-brightgreen?style=for-the-badge&logo=github)](https://github.com/yhatt/marp-cli-example/generate)

We already have [GitHub Actions workflow](.github/workflows/github-pages.yml) to build and deploy from `master` to `gh-pages` automatically. All you have got to [turn on GitHub Pages with `gh-pages` branch](https://docs.github.com/en/free-pro-team@latest/github/working-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site) from **"Settings"** tab.

### <img src="https://icongr.am/simple/netlify.svg?colored" width="24" height="24" valign="bottom" /> [Netlify]

Push **"Deploy to netlify"** button. [Netlify] will create your repository based on this example and host website from `master` branch automatically.

[![Deploy to Netlify](./assets/netlify-deploy-button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/yhatt/marp-cli-example)

### <img src="https://icongr.am/simple/zeit.svg" width="24" height="24" valign="bottom" /> [Vercel]

Push **"Deploy"** button. [Vercel] can choose to create your repository based on this example.

[![Deploy to Vercel](https://vercel.com/button)](https://vercel.com/import/project?template=https://github.com/yhatt/marp-cli-example)

> :information_source: To enable the auto-generated open graph image in Vercel, you have to turn on ["Automatically expose System Environment Variables"](https://vercel.com/docs/concepts/projects/environment-variables#system-environment-variables) in your Vercel project dashboard.

## How to write

For Marp slide deck features, please see the documentation of [Marpit Markdown](https://marpit.marp.app/markdown), [the features of Marp Core](https://github.com/marp-team/marp-core#features), and the default example in [`PITCHME.md`](https://raw.githubusercontent.com/yhatt/marp-cli-example/master/PITCHME.md) for .

You have to install [Node.js](https://nodejs.org/) and run `npm i` at first if you want to write slide deck with [Marp CLI].

### Edit deck

Just edit **[`PITCHME.md`](./PITCHME.md)**!

#### Preview deck

**[Marp for VS Code]** extension is the best partner for writing Marp slide deck with live preview.

<p align="center">
  <a href="https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode">
    <img src="https://raw.githubusercontent.com/marp-team/marp-vscode/master/docs/screenshot.png" width="500" />
  </a>
</p>

**You can try edit and preview on the web now!** Open https://github.dev/yhatt/marp-cli-example/blob/master/PITCHME.md or hit <kbd>.</kbd> key on this repository, and install [Marp for VS Code] extension.

[marp for vs code]: https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode

#### Preview via CLI

```bash
npm run start
```

It will be opened preview window via installed Google Chrome, and track change of `PITCHME.md`.

### Assets and themes

- `assets` directory can put your assets for using in the deck. (e.g. Image resources)
- `themes` directory can put [custom theme CSS](https://marpit.marp.app/theme-css). To use in the deck, please change `theme` global directive.

### Build deck via CLI

```bash
npm run build
```

The built assets will output to `public` folder.

#### Build per assets

```bash
npm run deck      # Output static HTML to public/index.html
npm run og-image  # Output image for Open Graph to public/og-image.jpg
```

## LICENSE

[WTFPL](/LICENSE)
