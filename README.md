# Obsidian Git

Plugin that allows you to back up your [Obsidian.md](https://obsidian.md) vault to a remote Git repository (e.g. private repo on GitHub).

Requirements, installation steps (including setup for mobile), tips and tricks, common issues and more can be found in the [documentation](https://publish.obsidian.md/git-doc).

For mobile users see [Mobile](#mobile) section below.

## Highlighted Features

-   Automatic vault backup every X minutes
-   Pull changes from remote repository on Obsidian startup
-   Assign hotkeys for pulling/pushing changes to a remote repository
-   Manage different repositories via Git submodules (after enabling this feature in settings)
-   The Source Control View allows you to stage and commit individual files. It can be opened with the `Open Source Control View` command.
-   The History View shows the commits and their changed files. So basically an integrated `git log`. It can be opened with the `Open History View` command.
-   For viewing the history of a file, I strongly recommend you the [Version History Diff](obsidian://show-plugin?id=obsidian-version-history-diff) plugin

### Source Control View

![Source Control View](https://raw.githubusercontent.com/denolehov/obsidian-git/master/images/source-view.png)

### History View

![History View](https://raw.githubusercontent.com/denolehov/obsidian-git/master/images/history-view.png)

## Available Commands

-   Changes
    -   `List changed files`: Lists all changes in a modal
    -   `Open diff view`: Open diff view for the current file
    -   `Stage current file`
    -   `Unstage current file`
-   Commit
    -   `Commit all changes`: Only commits all changes without pushing
    -   `Commit all changes with specific message`: Same as above, but with a custom message
    -   `Commit staged`: Commits only files that have been staged
    -   `Commit staged with specific message`: Same as above, but with a custom message
-   Backup
    -   `Create Backup`: Commits all changes. If "Push on backup" setting is enabled, will also push the commit.
    -   `Create Backup with specific message`: Same as above, but with a custom message
    -   `Create backup and close`: Same as `Create Backup`, but if running on desktop, will close the Obsidian window. Will not exit Obsidian app on mobile.
-   Remote
    -   `Push`
    -   `Pull`
    -   `Edit remotes`
    -   `Remove remote`
    -   `Clone an existing remote repo`: Opens dialog that will prompt for URL and authentication to clone a remote repo
    -   `Open file on GitHub`: Open the file view of the current file on GitHub in a browser window. Note: only works on desktop
    -   `Open file history on GitHub`: Open the file history of the current file on GitHub in a browser window. Note: only works on desktop
-   Local
    -   `Initialize a new repo`
    -   `Create new branch`
    -   `Delete branch`
    -   `CAUTION: Delete repository`
-   Source Control View
    -   `Open source control view`: Opens side pane displaying [Source control view](#sidebar-view)
    -   `Edit .gitignore`
    -   `Add file to .gitignore`: Add current file to .gitignore

## Desktop

## Authentication

Authentication may require additional setup. See more in the [Authentication documentation](https://publish.obsidian.md/git-doc/Authentication)

### Obsidian on Linux

-   ⚠ Snap is not supported.
-   ⚠ Flatpak is not recommended, because it doesn't have access to all system files.

Please use AppImage instead ([Linux installation guide](https://publish.obsidian.md/git-doc/Installation#Linux))

## Mobile

### Restrictions of the mobile version

I am using [isomorphic-git](https://isomorphic-git.org/), which is a re-implementation of Git in JavaScript, because you cannot use native Git on Android or iOS.

-   SSH authentication is not supported ([isomorphic-git issue](https://github.com/isomorphic-git/isomorphic-git/issues/231))
-   Repo size is limited, because of memory restrictions
-   Rebase merge strategy is not supported
-   Submodules are not supported

### Performance on mobile

> **Warning**
> Depending on your device and available free RAM, Obsidian may crash on clone/pull. I don't know how to fix this. If that's the case for you, I have to admit this plugin won't work for you. So commenting on any issue or creating a new one won't help. I am sorry.

**Setup:** iPad Pro M1 with a [repo](https://github.com/Vinzent03/obsidian-git-stress-test) of 3000 files reduced from [10000 markdown files](https://github.com/Zettelkasten-Method/10000-markdown-files)

The initial clone took 0m25s. After that, the most time consuming part is to check the whole working directory for file changes. On this setup, checking all files for changes to stage takes 03m40s. Other commands like pull, push and commit are very fast (1-5 seconds).

The fastest way to work on mobile if you have a large repo/vault is to stage individual files and only commit staged files.

## Contact

The Line Authoring feature was developed by [GollyTicker](https://github.com/GollyTicker), so any questions may be best answered by him.

If you have any kind of feedback or questions, feel free to reach out via GitHub issues or `@Vinadon` on [Obsidian Discord server](https://discord.com/invite/veuWUTm).

This plugin was initial developed by [denolehov](https://github.com/denolehov). Since March 2021, it is [Vinzent03](https://github.com/Vinzent03) who is developing on this plugin.

If you want to support me ([Vinzent03](https://github.com/Vinzent03)) you can support me on Ko-fi

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/F1F195IQ5)
