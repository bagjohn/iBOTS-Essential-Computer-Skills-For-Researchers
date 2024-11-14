
```
mkdir -p git_exercise
ls
cd git_exercise/
```

```
git init
```

```
git status
```


```
echo 'Hello World!' > hello_world.txt
```

```
git status
```

```
git add hello_world.txt
```

```
git commit -m 'Add hello_world.txt file'
```

```
git log --oneline
```


```
echo 'Adding more text to the file!' >> hello_world.txt
```

```
git diff
```

```
git log
```


```
git branch feature-branch
```

```
git checkout feature-branch
```

```
git branch
```

```
git checkout main
```

```
git merge feature-branch
```