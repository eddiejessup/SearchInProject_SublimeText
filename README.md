**NOTE: This is a fork of [this plugin](https://github.com/leonid-shevtsov/SearchInProject_SublimeText) that I'm using as a base for my own hacky plugin for heustically searching Haskell codebases. It isn't meant for public consumption, so probably you don't want to use it.**

# Search In Project

<a href='https://ko-fi.com/X8X19BQH' target='_blank'><img height='36' style='border:0px;height:36px;' src='https://az743702.vo.msecnd.net/cdn/kofi1.png?v=0' border='0' alt='Buy Me a Coffee at ko-fi.com' /></a>

![Search in Project screencast](https://raw.githubusercontent.com/leonid-shevtsov/SearchInProject_SublimeText/screencast/screencast.gif)

This plugin for [Sublime Text 2 and 3](http://www.sublimetext.com/) lets you use your favorite search tool (`grep`, `ack`, `ag`, `pt`, `rg`, `git grep`, or `findstr`) to find strings aross your entire current Sublime Text project.

It opens a quick selection panel to browse results, and highlights matches inside files.

## Usage

* Use the key binding (`⌘⌥⇧F` on OS X, `Ctrl+Alt+Shift+F` on Windows and Linux), or
* Call the "SearchInProject: Search" command;
* Enter the search query;
* Hit `Enter` (`Return`). You'll be presented with a "quick select" panel with the search results. Select any file from that panel (it supports fuzzy searching) to go to the match. The search string will be highlighted with an outline and a circle symbol in the gutter area.
* The last item on the quick select panel is "List results in view". Pick it to see results in a regular editor view. (Tip: if you enter three ticks ("`") in the search box - it's going to be to be the first item.)

If you select text and run Search In Project, the program will pre-fill the search string with the selection text. For an example, to search for a word project-wide, press the following buttons: `⌘D, ⌘⌥⇧F, ↩`.

If you run Search In Project again, the program will remember the last search string, so the next search will be an ↩ away.

**Important note for Windows users: the current release has known issues with running executables, and I would appreciate any bug reports from the field.**

## Installation

[Package Control](http://sublime.wbond.net): install package **Search in Project** (this is the recommended method)

Manual installation: download an [archive of the repository](https://github.com/leonid-shevtsov/SearchInProject_SublimeText/archive/master.zip), and unzip into the Sublime Text Packages folder.

### Installing search engines

My idea is that if you use this plugin it's because you already use one of the superior search engines like [The Silver Searcher](https://github.com/ggreer/the_silver_searcher) and want to use it from within Sublime Text.

The supported search engines are:

| Name                                                                                      | Description                                                                                                                                                   | Search in Project key   |
| ----------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------- |
| **[pt (The Platinum Searcher)](https://github.com/monochromegane/the_platinum_searcher)** | **fast, has binaries for every platform, recommended.**                                                                                                       | `the_platinum_searcher` |
| **[ag (The Silver Searcher)](http://geoff.greer.fm/ag/)**                                 | **equally fast, only 3rd party binaries for Windows, also recommended**                                                                                       | `the_silver_searcher`   |
| [ack](http://beyondgrep.com/)                                                             | not as fast as `pt` and `ag`, but still pretty good. Depends on perl, thus not so easy to install on Windows.                                                 | `ack`                   |
| [git grep](http://git-scm.com/docs/git-grep)                                              | packaged with Git and really fast, but only works in Git repositories. Recommended if you use Windows and Git and really don't want to install anything else. | `git_grep`              |
| [grep](https://en.wikipedia.org/wiki/Grep)                                                | fallback search tool available on Linux and OSX systems. Not recommended - just use the built-in Sublime Text search instead.                                 | `grep`                  |
| [findstr](https://technet.microsoft.com/en-us/library/Bb490907.aspx)                      | fallback search tool available on Windows. Not recommended - just use the built-in Sublime Text search instead.                                               | `find_str`              |

**You need to choose the engine that you want to use in the configuration file. The default is the one that available on every system, but it is easily the worst.**

## Configuration

Configuration is stored in a separate, user-specific `SearchInProject.sublime-settings` file. See the default file for configuration options; links to both could be
found in the main menu in `Preferences -> Package Settings -> Search In Project`.

## Issues with locating executables

If Search In Project has problems with locating executables in Mac, install the [Fix Mac Path plugin](https://github.com/int3h/SublimeFixMacPath).

You can always configure the full path to any search engine in the settings, as a catch-all solution.

---

Made by [Leonid Shevtsov](http://leonid.shevtsov.me)
