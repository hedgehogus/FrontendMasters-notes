git config --get --global init.defaultBranch
git config --global --unset init.defaultBranch

git config --global rerere.enabled
git config --global --unset rerere.enabled

- **--global** flag will ensure you set this key value for all future uses of git and repos
- **user.name and user.email** are the keys used in creating a commit tied to you
- to add a key value, execute ```git config -add --global <key> "<value>"```
- you can view any value of git config by executing ```git config --get <key>```

git config --get user.email
git config --get user.name

## listing out values

``git config --list`` where it will list out the entire config
``git config --get-regexp <regex>`` - this takes a pattern and looks for all names matching

## remove values
``git config --remove-section sectionname``

## unset values 
``--unset`` - unsets one key
``--unset-all`` - unsets all matching keys

## change default branch name
``git config -add --global init.defaultBranch 'branchname'``
