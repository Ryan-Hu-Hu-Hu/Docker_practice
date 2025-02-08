# Container implementation
Clone the tutorial image and run it in a separate directory (not inside this repository):
```bash
# Clone in a different directory, not inside this repository
cd ..
git clone https://github.com/docker/getting-started-todo-app
cd getting-started-todo-app
docker compose watch
```
If you already cloned it, the following shows how to remove the original getting-started-todo-app
```bash
git rm --cached Implementation/getting-started-todo-app
rm -rf Implementation/getting-started-todo-app
```

If using VSCode or cursor to run the above code, 