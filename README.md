# tag-test
Testing tag deletion command and their effects before trying it on real repos

tag 1
no tag
tag 2 
tag 3
no tag
tag 4


get list of remote tags ALL
	git ls-remote --tags origin | awk ' /^(.*)$/ {print $2} '
	
get list of remote tags VERSIONED
	git ls-remote --tags origin | awk ' /^(.*)v[0-9].*$/ {print $2} '
	
get local tags
	git tag -l
	
get list of local tags VERSIONED
	git tag | grep -E '^(.*)v[0-9].*$'

push tags
	git push origin --tags
	
-----------------------------------------------


Listing TagsGet All Remote Tags
	* git ls-remote --tags origin | awk ' /^(.*)$/ {print $2} '

Get Remote Tags - Using awk to filter tag name
	* git ls-remote --tags origin | awk ' /^(.*)v[0-9].*$/ {print $2} '

Get All Local Tags
	* git tag -l

Get Local Tags - Using grep to filter tag name
	* git tag | grep -E '^(.*)v[0-9].*$'

Creating & Pushing TagsCreate a Tag
	* git tag myTag

Push Tags To Remote
	* git push origin --tags

Deleting TagsDelete All Local Tags
	* git tag -d `git tag | grep -E '.'`

Delete Local Tags - Using grep to filter tag name
	* git tag -d `git tag | grep -E '^(.*)v[0-9].*$'`

Delete All Remote Tags
	* git ls-remote --tags origin | awk '/^(.*)$/ {print ":" $2}' | xargs git push origin



Delete Remote Tags - Using awk to filter tag name
	* 
git ls-remote --tags origin | awk '/^(.*)v[0-9].*$/ {print ":" $2}' | xargs git push origin












