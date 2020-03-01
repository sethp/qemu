# Beagle* Qemu Fork

Integrates limited beagleboard (+omap3) support from http://git.linaro.org/qemu/qemu-linaro.git

Somewhat useful aliases (with `git remote add qemu-linaro http://git.linaro.org/qemu/qemu-linaro.git`):

```
[alias]
	mergelf = "!f() { \
  if ! [ -z \"$(git status --porcelain $1)\" ] ; then echo refusing to merge modified file $1 ; return ; fi ; \
  git show $(git merge-base origin/master qemu-linaro/master):$1 > $1.base ; \
  git show qemu-linaro/master:$1 > $1.linaro ; \
  git merge-file $1 $1.base $1.linaro ; \
  rm $1.base $1.linaro ; \
}; f"
	coql = checkout qemu-linaro/master --
	grepql = "!git grep $@ qemu-linaro/master && :"
```

## TODO

See TODO[Seth] in the root.
