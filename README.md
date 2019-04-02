# Safari Cache Bug

There is a cache corruption bug that has been reported in a number of places. It seems to be a race condition triggered when window.location is changed while a resource is being fetched. There may be a number of other scenarios that trigger this.

This repo is an SSCCE which reproduces the bug.

Places where this has been reported

* https://github.com/FortAwesome/Font-Awesome/issues/7770
* https://stackoverflow.com/questions/22751758/font-awesome-icons-not-working-in-osx-safari
* https://github.com/google/fonts/issues/1616

This is being investigated at https://bugs.webkit.org/show_bug.cgi?id=194251

# How to use this repo

- Clone this repo
- Open a file browser and load index.html with Safari. The page will redirect
- Click back button as prompted

Expected behavior - the icon should be shown

Actual behavior - the text is shown b/c the cache is corrupted.

# What does this bug look like?

![Repro](https://raw.githubusercontent.com/doanythingfordethklok/safari-cache-bug/master/repro.gif)

