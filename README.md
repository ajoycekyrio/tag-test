# tag-test
Testing tag deletion command and their effects before trying it on real repos

tag 1
no tag
tag 2 
tag 3
no tag
tag 4


get list of tags
	git ls-remote --tags origin | awk ' /^(.*)$/ {print $2} '