```
git remote add origin REMOTE_REPOSITORY_URL
```

```
git remote -v
```


```
git push -u origin main
```


```
git pull origin main
```


```
# 1. Create a new branch called 'feature-1' (run in terminal)
git branch feature-1
```


```
# 2. Switch to the new branch 'feature-1' (run in terminal)
git checkout feature-1
```



```
echo 'Hello from feature-1 branch!' > hello_world.txt
```



```
# 3. Stage the change in 'feature-1' branch (run in terminal)
git add hello_world.txt
```


```
# 4. Commit the change in 'feature-1' branch (run in terminal)
git commit -m 'Change hello_world.txt in feature-1 branch'
```


```
# 5. Switch back to the main branch (run in terminal)
git checkout main
```


```
echo 'Hello from main branch!' > hello_world.txt
```



```
# 6. Stage the change in 'main' branch (run in terminal)
git add hello_world.txt
```


```
# 7. Commit the change in 'main' branch (run in terminal)
git commit -m 'Change hello_world.txt in main branch'
```


```
# 8. Merge 'feature-1' into 'main' (run in terminal)
git merge feature-1
```


```
# 9. Stage the resolved file (run in terminal)
git add hello_world.txt
```



```
# 10. Commit the resolved merge conflict (run in terminal)
git commit -m 'Resolved merge conflict in hello_world.txt'
```


```
# 11. View the commit history (run in terminal)
git log --oneline
```


```
# 11. View the commit history (run in terminal)
git push
```

