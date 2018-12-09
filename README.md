# svn-xattr
A command-line utility to facilitate using the Subversion VCS to manage files with extended attributes (a.k.a. xattrs, metadata, macOS Resource Forks, macOS Rez, macOS File Type and Creator, AppleSingle, AppleDouble, Finder information, detritus).

## Installation
Via Homebrew:

    brew install smokris/svn-xattr/svn-xattr

## Example: storing a macOS Alias in a Subversion repo
Say you've created a macOS Alias (created with Finder; a.k.a. Bookmark; not to be confused with symlink) called `my-alias` in your `working-copy` folder.

```bash
cd working-copy
svn add my-alias
svn-xattr update my-alias
svn commit
```

Then, when checking out the repo:
```bash
svn update
svn-xattr restore
```
