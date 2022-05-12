# git-story
Tell the story of your Git project by creating video animations (.mp4)
of your commit history directly from your Git repo.

## Use cases
- Visualizing Git projects
- Sharing desired parts of your workflow with your team
- Creating animated Git videos for blog posts or YouTube
- Helping newer developers learn Git

## Features
- Run a simple command in the terminal to generate a custom Git animation (.mp4) from your repo
- Specify any commit id or ref to start animating from (default: `HEAD`)
- Specify the number of commits to include (default: `8`)
- Ref labels are drawn by default for `HEAD`, branch names, and tags
- Simple branching structures (1 or 2 branches)
- Add custom branded intro/outro sequences if desired

## Video animation example
https://user-images.githubusercontent.com/49353917/168178222-583167f6-9e86-4e0b-a1ba-3a8c57aa3abe.mp4

## Requirements
* Python 3.9 or greater
* Pip (Package manager for Python)
* [Manim (Community version)](https://www.manim.community/)
* GitPython

## Quickstart
1) Install [manim and manim dependencies for your OS](https://www.manim.community/)

2) Install GitPython

```console
$ pip3 install GitPython
```

3) Install `git-story`:

```console
$ pip3 install git-story
```

3) Browse to the Git repository you want create an animation from:

```console
$ cd path/to/project/root
```

4) Run the program:

```console
$ git-story
```

5) A default animation `.mp4` file will be created using the most recent 8 commits on your checked-out Git branch.

6) Use command-line options for customization, see usage:

```console
$ git-story -h

usage: git-story [-h] [--commits COMMITS] [--commit-id COMMIT_ID] [--hide-merged-chains] [--reverse] [--title TITLE] [--logo LOGO] [--outro-top-text OUTRO_TOP_TEXT]
                 [--outro-bottom-text OUTRO_BOTTOM_TEXT] [--no-intro] [--no-outro] [--max-branches-per-commit MAX_BRANCHES_PER_COMMIT] [--max-tags-per-commit MAX_TAGS_PER_COMMIT]

optional arguments:
  -h, --help            show this help message and exit
  --commits COMMITS     The number of commits to display in the Git animation (default: 8)
  --commit-id COMMIT_ID
                        The ref (branch/tag), or first 6 characters of the commit to animate backwards from (default: HEAD)
  --hide-merged-chains  Hide commits from merged branches, i.e. only display mainline commits (default: False)
  --reverse             Display commits in reverse order in the Git animation (default: False)
  --title TITLE         Custom title to display at the beginning of the animation (default: Git Story, by initialcommit.com)
  --logo LOGO           The path to a custom logo to use in the animation intro/outro (default: logo.png)
  --outro-top-text OUTRO_TOP_TEXT
                        Custom text to display above the logo during the outro (default: Thanks for using Initial Commit!)
  --outro-bottom-text OUTRO_BOTTOM_TEXT
                        Custom text to display below the logo during the outro (default: Learn more at initialcommit.com)
  --no-intro            Omit the intro sequence from the animation (default: False)
  --no-outro            Omit the outro sequence from the animation (default: False)
  --max-branches-per-commit MAX_BRANCHES_PER_COMMIT
                        Maximum number of branch labels to display for each commit (default: 2)
  --max-tags-per-commit MAX_TAGS_PER_COMMIT
                        Maximum number of tags to display for each commit (default: 1)
```

## Command Examples
Default - draw 8 commits starting from `HEAD`, from oldest to newest:

```console
$ cd path/to/project/root
$ git-story
```

Customize the start commit and number of commits, and reverse their display order:

```console
$ cd path/to/project/root
$ git-story --commit-id a1b2c3 --commits=6 --reverse
```

Add an intro with custom title and logo:

```console
$ cd path/to/project/root
$ git-story --commit-id dev --commits=10 --show-intro --title "My Git Repo" --logo "~/logo.png"
```

Add an outro with custom text and logo:

```console
$ cd path/to/project/root
$ git-story --show-outro --outro-top-text "My Git Repo" --outro-bottom-text "Thanks for watching!" --logo "~/logo.png"
```

## Installation
See **QuickStart** section for details on installing manim and GitPython dependencies. Then run:

```console
$ pip3 install git-story
```

## Learn More
Learn more about this tool on the [git-story project page](https://initialcommit.com/tools/git-story).

## Authors
**Jacob Stopak** - on behalf of [Initial Commit](https://initialcommit.com)
