# Safari Cache Bug

There is a cache corruption bug that has been reported in a number of places. It seems to be a race condition triggered when window.location is changed while a resource is being fetched.

This repo is an SSCCE which reproduces the bug.

Places where this has been reported
https://github.com/FortAwesome/Font-Awesome/issues/7770
https://github.com/bramstein/fontfaceobserver/issues/35
https://stackoverflow.com/questions/22751758/font-awesome-icons-not-working-in-osx-safari

# How to use this repo

- Clone this repo
- Open a file browser and load index.html with Safari. The page will redirect
- Click back button as prompted

Expected behavior - the icon should be shown

Actual behavior - the text is shown b/c the cache is corrupted.
