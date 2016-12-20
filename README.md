# git file-history

This script provides a Git subcommand to retrieve commit history for a particular file
in a repository.
This is particularly useful for preserving the commit history of a file when moving it
to another repository.
To generate a patch file, pipe the output to a .patch file.
Otherwise the output is displayed using Git's default pager.

## Installation

Put the `git-file-history` file anywhere in your path.
That's it!

## Example

Say you have a repository of recipes and you want to move the section for greens to its
own separate repository, while preserving full authorship information.

```bash
cd ~/recipes
git file-history greens/salad.txt > ~/salad.patch
mkdir ~/leafy-recipes && cd ~/leafy-recipes
git init
git am --committer-date-is-author-date < ~/salad.patch
```
