# ![soapbox](https://soapboxjs.github.io/logo.png)

**A static site framework, which is:**

1. Lean
2. Flexible
3. Modular
4. Modern
5. Robust
6. Static &
7. Blog-aware

> A detailed origin story of soapbox is coming soon.

# Usage
### Install soapbox CLI
```
sudo npm install -g @soapboxjs/cli
```

### Create a project instance
```
soapbox init <directoryName>
cd <directoryName>
```

### Then initiate contents
```
# If you're new to soapbox, then use the default preset
edit contents/posts/<postName>.md

# If you're returning user, with existing contents 
rm -rf contents/
git clone <repoURL> contents

# If you're migrating from other platform/framework, or
# You want to understand better, then check out the wiki
```

### Start development server
```
# Install dependencies
npm install

# Generate in watch mode & serve over localhost:8888
npm run serve
```

### Build and publish
```
# Generate production `./build`
npm run build

# Push latest `./build` to `gh-pages`
npm run publish
```

# Looking under the hood
Fragments of **documentation for each part of the repo are found in their own directories, in form of `README.md` files** as comprehensive summary. The codes/files are also inline-commented individually, for deep-diving into understanding their purpose and process. Feel free to file issues or, send pull requests if you want to extend the documentation for the project.

This main `README.md` file serves as the masthead for docs, and contains the basic/common information about the repository.

## Overview of the file/folder structure
```
│
├── bin
│   ├── # automation scripts live here
│   └── # as a user, you can safely ignore this directory
│
├── contents
│   ├── app
│   │   ├── index.html  # generates site entrypoint index page
│   │   ├── pages.html  # generates individual html pages
│   │   ├── posts.html  # generates posts as html files
│   │   ├── ──────────
│   │   ├── # theming is part of app-shell
│   ├── assets
│   │   ├── favicon.ico
│   │   ├── ──────────
│   │   ├── # and any other static file to be served as is
│   │   ├── # images, fonts, styles, scripts etc go in here
│   │   └── # will be merged with generated `prep` directory
│   └── data
│       ├── pages
│       │   ├── pagename(s).md
│       │   ├── ──────────
│       │   └── # custom pages go in here, as *.md files
│       └── posts
│           ├── postname(s).md
│           ├── ──────────
│           └── # posts go in here, as *.md files
│
├── prep
│   ├── data            # this is where generated JSON files go
│   ├── <static>        # static files fetched from assets dir
│   ├── config/script   # user configurations & customizations
│   ├── index.html      # landing page template with theme
│   ├── pages.html      # sub-page template with theme
│   ├── posts.html      # posts template with theme
│   ├── ──────────
│   ├── # This is an intermediate step, result of `prep` command
│   └── # This phase helps separate framework vs user preferences
│
└── build
    ├── data            # Generated JSONs for partial fetching
    ├── <static>        # static files fetched from assets dir
    ├── [<posts>]       # posts' dirs, with index.html inside
    ├── [<pages>]       # pages' dirs, with index.html inside
    ├── index.html      # landing page with posts; list & pages
    ├── ──────────
    └── # This is what you want to publish on `gh-pages`
```

## Scripts and commands
```
@TODO: list of commands and their operations go in here
```
In order to create custom commands/behaviors, check out `scripts` section of `package.json` for the commands & look inside `bin/` directory for their related script files.
