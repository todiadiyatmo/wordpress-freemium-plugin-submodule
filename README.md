#Wordpress Freemium Plugin Submodule
Concept of using submodule on developing wordpress freemium plugin/theme.

##Source 
Please understand git submodule before using this concept : [https://chrisjean.com/git-submodules-adding-using-removing-and-updating/](https://chrisjean.com/git-submodules-adding-using-removing-and-updating/)


##Preface
Most of WordPress developer fund their live by releasing freemium blog/plugin. In this freemium model, usually the codebase between the free and premium one is nearly identical.

##Git Repository List

1. `feremium-submodule-core`->
	This is where your core code file lies.
2. `freemium-submodule-premium`
	Repository for premium only code.
3. `freemium-dist-free`
	Release distribution in wordpress.org
4. `freemium-dist-premium`
	Your premium pack, where you generate some revenue :D

##Strategy

1. `freemium-dist-premium`
	**Contains :**  
	- `freemium-submodule-core`
	- `freemium-submodule-premium`
	
2. `freemium-dist-free`
	**Contains :**
	- `freemium-submodule-core`

##Sample Git Code for `freemium-dist-premium`

```git
git init
git remote add upstream git@github.com:todiadiyatmo/freemium-dist-premium
git submodule add git@github.com:todiadiyatmo/freemium-submodule-core core
git submodule add git@github.com:todiadiyatmo/freemium-submodule-premium extra
git submodule init
git submodule update
git add core
git add extra
git commit -m "first commit"
git push origin master -f
```
