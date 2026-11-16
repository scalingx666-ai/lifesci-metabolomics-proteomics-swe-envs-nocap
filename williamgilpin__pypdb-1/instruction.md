# Issue

**Title:** Add __init__ file and alter import statements

## Description

Hey, thanks for putting this together, I'm sure I'll use it quite a bit. I noticed that there wasn't an init file in the pydbp directory. It's not strictly necessary, but if you want to add additional packages then it'll definitely make life easier. Will also make importing the module a bit cleaner:

``` python
>>> import pypdb
>>> pypdb.get_all()
```

instead of the way its done in the demos:

``` python
>>> from pypdb.pypdb import *
>>> get_all()
```

In general `from module import *` [isn't great practice](http://stackoverflow.com/questions/2360724/in-python-what-exactly-does-import-import) as it imports all the function names in that module which makes your namespace a lot more cluttered. In the case of something like numpy, that's a ton of names and increases the risk of accidentally overwriting something. So I changed that in the import statements of pypdb.py.  Having said that, I couldn't find any functions (didnt look very hard) using either numpy or matplotlib, so If they're in and I've missed them you'd need to add the necessary `np.` or `plt.` prefix, or don't import them in the first place.

Obviously feel free to ignore all the above, just figured i'd chuck in my two cents.

Cheers,
Jon

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `1b1093ff197f`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.