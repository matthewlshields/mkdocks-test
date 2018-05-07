
Clone the repository and enter the directory

```
git clone ...
cd 
```


### Publish the GitHub Pages

> Perform the follow steps from the root of the project

Create a working tree for the compiled GitHub Pages

```
git worktree add -b gh-pages ./gh-pages
```
You may notice the above step copied the contents of the master branch to the gh-pages branch. This is okay because the build step will overwrite the contents.

Build the pages using the ```-d``` flag to specify the output directory
```
docker run --rm -it -p 8000:8000 -v ${PWD}:/docs squidfunk/mkdocs-material build -d gh-pages
```

Change to the gh-pages directory ```cd gh-pages```
A ```git status``` will show the previous contents as being removed that the compiled contents as being present

Do a ```git add .``` and a ```git commit -m``` Don't forget your message

Push the changes ```git push -u origin gh-pages```

PRESTO! The gh-pages branch is on the repo and serving up content.


