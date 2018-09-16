# ![soapbox](assets/logo.png)

## What is soapbox?
- **Static blog engine/generator**
- Small, performant, non-opinionated
- (Almost) drop-in replacement for Jekyll
- With [SPA](https://en.wikipedia.org/wiki/Single-page_application)-like content loading & navigation
- And architectural simplicity to encourage tinkering

## Why is soapbox?
Because the creator of `soapbox` wasn't happy with any single blogging platform/framework/engine/generator that does everything he wishes it to; and making yet another engine from scratch was easier than clobbering the existing ones to fit the need.

The blog had to be:

<dl>
  <dt>Lean</dt>
  <dd>Lean - in this context - is an intentionally overloaded term. It ordains <b>fast</b>, <b>focused</b>, <b>minimalistic</b>, <b>performant</b> & <b>uncompromising</b> behavior. Leanness, here, pursues that the <em>tool should never become the bottleneck of the product</em>.</dd>
  <dt>Flexible</dt>
  <dd>Differences in choices are to be respected, as long as it doesn't require going out of the way of leanness. The <code>soapbox</code> is not meant to be opinionated; although there are some preset defaults set here and there for now, those aren't meant to be permanent.</dd>
  <dt>Modular</dt>
  <dd>Flexibility is only practical, when the tool is modular enough to accommodate it. Replacing and reusing parts of the whole isn't only expected, it's encouraged.</dd>
  <dt>Modern</dt>
  <dd>Tools of today, and tools of the future should not cause the developer to rip their hairs off, working with <code>soapbox</code>. Modern is, one, that is capable of surfing the tide of time.</dd>
  <dt>Robust</dt>
  <dd>Even though, robustness is grossly a by-product of leanness, one can be lean without specificaly being robust. We seek both. <b>Availability</b>, <b>efficiency</b>, <b>portability</b>, <b>predictability</b> &amp; <b>stability</b> of <code>soapbox</code> can not be compromised.</dd>
  <dt>Static</dt>
  <dd>Most of what has been sought-after so far, is easier done as a server-side application. Which is why most popular blogging platforms require dynamic server & runtime, or the static ones make compromises along the way for pragmatism. Both alternatives are unacceptable for us.</dd>
  <dt>Blog-aware</dt>
  <dd>The main intent is to make a blog engine, afterall. It should be able to comprehend and handle the conventions, which are specific to blogs (slugs, tags, comments etc).</dd>
</dl>

# Using soapbox
- Fork and/or clone the repo: `git clone https://github.com/debloper/soapbox`
- Copy all your posts as `*.md` files to `contents/posts/` directory
- [optional] copy all the pages into `contents/pages/` directory
- [optional] edit `theme/` files, or put your own (detailed later)
- [optional] copy favicon, styles, scripts, images into `assets/`

Once you're through adding the contents:
- run `npm install` to install dependencies
- run `npm run build` to generate static site in `dist/`
- run `npm run serve` while developing, to view it in browser
- run `npm run publish` to push the generated content to `gh-pages`

---

## In future
When there's sufficient user-base to make it worth it, a CLI utility will be created to bootstrap and manage `soapbox` blogs. That will make it easy to update the core software (leaving content as is), instead of having to use `git pull` and end up facing merge-conflicts.

# Looking under the hood
Fragments of **documentation for each part of the repo are found in their own directories, in form of `README.md` files** as comprehensive summary. The codes/files are also inline-commented individually, for deep-diving into understanding their purpose and process. Feel free to file issues or, send pull requests if you want to extend the documentation for the project.

This main `README.md` file serves as the masthead for docs, and contains the basic/common information about the repository.

## Overview of the file/folder structure
```
├── assets
│   ├── favicon.ico
│   ├── ──────────
│   ├── # and any other static file to be served as is
│   ├── # images, fonts, styles, scripts etc go in here
│   └── # will be merged with generated `dist` directory
│
├── bin
│   ├── # automation scripts live here
│   └── # as a user, you can safely ignore this directory
│
├── contents
│   ├── pages
│   │   ├── pagename(s).md
│   │   ├── ──────────
│   │   ├── # custom pages go in here, as *.md files
│   │   └── # compiled with `themes/pages.html` template
│   └── posts
│       ├── postname(s).md
│       ├── ──────────
│       ├── # posts go in here, as *.md files
│       └── # compiled with `themes/posts.html` template
│
├── dist
│   ├── data        # this is where generated JSON files go
│   ├── index.html  # the main/landing page
│   ├── ──────────
│   ├── # plus all the files/folders from assets directory
│   ├── # and all posts & pages folders, with index.html inside
│   └── # contents of this directory is your desired end-result
│
└── theme
    ├── home.html   # used for generating the `index.html` file
    ├── pages.html  # used for generating individual html pages
    ├── posts.html  # used for generating posts as html files
    ├── ──────────
    ├── # scripts and styles for the theme go into the `assets`
    ├── # it is upto you to pre/post-process scripts and styles
    ├── # data for rendering pages & posts come from `contents`
    ├── # edit these files to customize look & feel of the site
    └── # templates use dot.js (for now), it's not a constraint
```

## Scripts and commands
```
@TODO: list of commands and their operations go in here
```
In order to create custom commands/behaviors, check out `scripts` section of `package.json` for the commands & look inside `bin/` directory for their related script files.
