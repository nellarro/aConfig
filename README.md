# Dear Future, Self

Hey, Jenell. It's Jenell. 

You might need a new computer some day. Get your git aliases up to date, girl. 

-----

[user]
	name = Jenell Pizarro
	email = youremail@email.com
[alias]
	alog = log --abbrev-commit --pretty=format:"%C(yellow)%h\\ %ad%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --date=short
	b = branch
	branch-name = "!git rev-parse --abbrev-ref HEAD"
	cam = !git add -A && git commit -m
	clean-house= "!git fetch -p && for branch in `git branch -vv | grep ': gone]' | awk '{print $1}'`; do git branch -D $branch; done"
	cob = checkout -b
	com = checkout master
	cod = checkout develop
	co = checkout
	delete = branch -D
	la = "!git config -l | grep alias | cut -c 7-"
	last = checkout @{-1} // checks out the last branch you were on
	last-branch = checkout @{-1} // ^^ same just in case you forget
	pretty = log --pretty=format:"%C(yellow)%h\\ %ad%Cred%d\\ %Creset%s%Cblue\\ [%cn]" --decorate --date=short
	push-it = "!git push -u origin $(git branch-name)"
	save = !git add -A && git commit -m 'WIP...savepoint'
	undo = reset HEAD~1
	undo-commit = reset HEAD~1 --mixed
	unpush = "!git push origin :$(git branch-name)"
	plod = pull origin develop
	spring-clean = branch | egrep -v "master" | xargs git branch -D // removes branches that don't have remotes
	deep-clean = branch | grep -v 'master' |  xargs git branch -D
	difftool = gitk

[help]
	autocorrect = 35

[core]
	excludesfile = /Users/{{user}}/.gitignore_global
	editor = code --wait // use your favorite editor where {{code}} is. Let's be serious -- it's VSCode
[difftool "sourcetree"]
	cmd = opendiff \"$LOCAL\" \"$REMOTE\"
	path =
[mergetool "sourcetree"]
	cmd = /Applications/Sourcetree.app/Contents/Resources/opendiff-w.sh \"$LOCAL\" \"$REMOTE\" -ancestor \"$BASE\" -merge \"$MERGED\"
	trustExitCode = true
# [bin]
# LF=$'\\\x0A'
# BRANCH_NAME=$(git symbolic-ref --short HEAD)
#
# if [[ $BRANCH_NAME =~ .*\/IZEAEX-[0-9]* ]]; then
#
# 	NUMBER=$(echo $BRANCH_NAME | sed -E 's/.*-([0-9]+).*/\1/')
# 	MESSAGE="IZEAEX-$NUMBER"
# 	if [ $NUMBER ]; then
# 		sed -i.back "1s/^/$MESSAGE /" "$1"
# 	fi
# fi
[filter "lfs"]
	clean = git-lfs clean -- %f
	smudge = git-lfs smudge -- %f
	process = git-lfs filter-process
	required = true
  
  
-----
  
Love, 

Jenell



