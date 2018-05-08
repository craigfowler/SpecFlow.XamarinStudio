SpecFlow for MonoDevelop 7.4+

This is an unofficial "hacked" version of the SpecFlow-for-MonoDevelop repository.

I have this nominally producing a semi-working add-on for MonoDevelop v7.4.  I've made a few changes here (and to the dependent repositories) in order to get it to build.

## Dependencies
This repo depends upon two others:

* SpecFlow
* SpecFlow.VisualStudio

It does not include them as NuGet packages.  Because of this, I have frozen their "working versions" into this repo as submodules.  I appreciate that git submodules are not a great solution, but it does essentially document which versions of those other repos will work with this one.

## Incompatible files
Whilst using this solution in order to create the add-in, I had to move a couple of files "out of the way" temporarily so that the build would succeed.  For me (using MonoDevelop Debian package), these files were at:

```
/usr/lib/monodevelop/AddIns/MonoDevelop.UnitTesting/VsTestConsole/x86/msdia140.dll
/usr/lib/monodevelop/AddIns/MonoDevelop.UnitTesting/VsTestConsole/x64/msdia140.dll
```

Simply temporarily renaming them with `.bak` extensions whilst I use msbuild, and then renaming them back afterwards seems to work just fine.  I'm not sure why, but it worked for me, so I don't particularly care.

## NO WARRANTY
Just in case it's not clear, this repo contains some hacking-about I did to make this MonoDevelop add-in work for me.  I make no representations that it will work for anybody else. Indeed, I would not recommend anybody tries to use this work on any kind of production environment.  It might delete your work, kick your neighbour's dog and bring about a world war.  If you do try it, please do so on a dev environment which you don't mind losing.

## Credit where due
Jo Shields (@directhex) deserves recognitiion for helping me with some of the tougher parts of this.