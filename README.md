This are the sources for the www.opensuse.org startpage. 

The page is hosted at Novell: 130.57.4.24 (mehle@novell, scweber@novell.com)
The sources are hosted at: git@github.com:openSUSE/landing-page.git

The page uses SSI includes and a cronjob that creates the news part.

It also used to have a wysiwyg editor for the hot_stuff part which required to
run fix_permissions.sh after deployment in order to make the files writeable for
te editor. Most likely, the wysiwyg editor is not used anymore, so this can be
skipped.

note about translations: (reverse engineered by lnussel)
```bash
# install the tools
$ zypper in po4a
# add your stuff
$ vi en/en/whats_hot.html
# generate pot file
$ ./make_POT.sh
# remove old translations
$ echo */po/*.po|xargs rm
# merge new translations
$ ./make_PO_to_HTML.sh
# check what happened
$ git status
# remove the languages that vanished from languages.html
$ vi languages.html
```
