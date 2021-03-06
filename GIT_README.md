Some usefull custom git cmd 
---------------------------

Add it in .gitconfig file

```bash
[alias]
	# Show all commit tree 
	tree = log --graph --decorate --pretty=oneline --abbrev-commit --all
	
	# Update project without merge, remove delete branches
	update = "!u() { git fetch && git fetch -p -t; }; u"
	
	# Show the diff between the latest commit and the current state
	show = !"git diff-index --quiet HEAD -- || clear; git --no-pager diff --patch-with-stat"
	
	# Switch to a branch, creating it if necessary
	switch = "!f() { git checkout -b \"$1\" 2> /dev/null || git checkout \"$1\"; }; f"

	# Interactive rebase with the given number of latest commits
	interactive = "!r() { git rebase -i HEAD~$1; }; r"

[color]
       branch = auto
       diff = auto
       interactive = auto
       status = auto
```
