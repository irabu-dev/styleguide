# Style Guide for Git

## Branches

- Choosen names must be short and descriptive.

	# good
	$ git checkout -b laravel-passport-migration

	# bad - too vague
	$ git checkout -b fix-authentication

- Whenever possible, names should include a suffix corresponding to the issue identifier. 

	# GitHub issue #10
	$ git checkout -b laravel-passport-migration-10

- Use *dashes* to separate words.

- Branches must be deleted from remotes after being merged.

> **ProTip:** Use `git branch --merged | grep -v "\*"` to list merged branches.

## Commits

- Each commit should be a single logical change. Don't make several logical changes in one commit. For example, if a patch fixes a bug and optimizes the perfomance of a feature, split it into two separate commits.

> **ProTip:** Use `git add -p` to interactively stage specific portions of modified files.

- Don't split a single logical change into to several commits. For example, the implementation of a feature and its tests should be in the same commit.

- Commits should be ordered logically. For example, if commit X depends on changes done in commit Y, then commit Y should come before commit X.

### Messages

- Use the editor, not the terminal, when writing a commit message

	# good 
	$ git commit

	# bad
	$ git commit -m "Quick fix" 

Committing from the terminal encourages a mindset of having to fit everything in one line, which *almost* always results into a non-informative, ambigous, useless commit messages.

- The first line of the message should be *descriptive* yet *succint*. Ideally, it should be no longer than 50 characters. It should be capitalized and written in imperative present tense. It should not end with a period, because it is essentially a commit title. 

- The commit title is followed with a blank line and more thorough description. It should be wrapped in *72 characters* and explain *why* the change is needed, *how* it addresses the issue and what *side-effects* it might have.

It should also provide any pointers to related resources.

Ultimately, when writing a commit message, think about what you need to know if you ran across the commit in a year from now.