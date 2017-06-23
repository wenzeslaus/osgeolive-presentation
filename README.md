# OSGeoLive Presentation

Presentation about OSGeoLive and related projects

## Find out what files are unused

    diff -u <(grep -E 'img.*src="[^"]*"' index.html | sed -e 's/.*img.*src="\([^"]*\)".*/\1/g' | sort | uniq) <(find images | sort) | grep -v "^ " | sed 's/^+/git rm /g' | sed 's/^-/echo Missing: /g'

To actually execute the commands add:

    ... | xargs -L 1 xargs
