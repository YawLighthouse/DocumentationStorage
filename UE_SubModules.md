# Submodules with Unreal Engine

[BionicApe Submodule Document](https://bionicape.com/unreal-plugins-as-git-submodules/)

For cloning a plugin as a submodule to an Unreal Engine Project repo:
```
git submodule add https://github.com/[UserName]/[RepoName].git Plugins/[RepoName]
git submodule update --init --recursive
git commit -m "Added plugin: [Plugin]"
```
so for example if your unreal engine project was named NicksUEProject and you wanted to add a plugin named CoolUEPlugin(lets assume I'm also the owner of the repo) 
then you would do
```
cd NicksUEProject
git submodule add https://github.com/Oldsiren/CoolUEPlugin.git Plugins/CoolUEPlugin
git submodule update --init --recursive
git commit -m "Added plugin: CoolUEPlugin"
```

After cloning a repo with submodules, run these commands in this order:
```
1. git submodule init
2. git submodule update
```

To clone a repo with its submodules already included
```
git clone https://github.com/[UserName]/[RepoName].git --recursive
```

To update the path of a submodule
```
git submodule init
git mv [old path of submodule within the repo] [new path of submodule within the repo]
git submodule update
```

Deleting unused submodules requires you to remove the referenced lines in .gitsubmodules and .git/config:
```
rm -rf [submodule]-dir/
git add
git commit -m "Removing [Submodule]"
```

