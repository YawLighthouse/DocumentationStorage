# Submodules with Unreal Engine

[BionicApe Submodule Document](https://bionicape.com/unreal-plugins-as-git-submodules/)

# Cloning SubModule to repo

For cloning a plugin as a submodule to an Unreal Engine Project repo at the root folder:
```
cd [RootRepository]
git submodule add https://github.com/[UserName]/[RepoName].git Plugins/[RepoName]
git submodule update --init --recursive
git commit -m "Added plugin: [Plugin]"
```
Example: If your unreal engine project was named NicksUEProject and you wanted to add a plugin named CoolUEPlugin(lets assume you're also the owner of the repo) 
then you would do this at the root folder of the repository. The last line in this example is just a commit with the message, so you can use a git client after running the `update` command.
```
cd NicksUEProject
git submodule add https://github.com/YawLighthouse/CoolUEPlugin.git Plugins/CoolUEPlugin
git submodule update --init --recursive
git commit -m "I added the plugin: CoolUEPlugin"
```

To clone a repo with its submodules already included, you can just add the `--recursive` tag. 
Example:
```
git clone https://github.com/[UserName]/[RepoName].git --recursive
```

# Updating(pull) SubModules with remote

[ServerSide Link](https://www.theserverside.com/blog/Coffee-Talk-Java-News-Stories-and-Opinions/How-to-update-Git-submodules#:~:text=To%20update%20the%20Git%20submodules%20in%20your%20workspace,a%20git%20commit.%205%20Push%20back%20to%20origin.)

To update the path of a submodule
```
git submodule init
git mv [old path of submodule within the repo] [new path of submodule within the repo]
git submodule update
```

To update the submodule(make sure its located at the repository's root folder)
```
git submodule update --remote
```

# Removing SubModules

Deleting unused submodules requires you to remove the referenced lines in .gitsubmodules and .git/config: \
[Stack Overflow Link](https://stackoverflow.com/questions/1260748/how-do-i-remove-a-submodule) \
Removing the directory and from the .gitsubmodules file:
```
git rm [SubmoduleDirectory]
```
Removing fromt the git config:
```
git config --remove-section submodule.[SubmoduleDirectory]
```

# Pushing Updates to a SubModule
There is a general rule to always do things in branches, so to do this you would have to make a branch on that submodule(I recommend naming it the same as yours so its easier to find) and then push to that branch, you can commit files like normal though but you have to do it through commands.

First commit your files in the submodule
```
cd [SubmoduleDirectory]
git commit -a
```
Then push those changes
```
git push origin HEAD:[BranchName]
```

