# Container implementation
Clone the tutorial image and run it:
#### Method 1: Direct clone the tutorial repository if you use **Docker Desktop** which is introduced in Docker's tutorial

```bash
git clone https://github.com/docker/getting-started-todo-app
cd getting-started-todo-app
docker compose watch
```
 
#### Method 2: Add tutorial by submodule, trying this method can prevent the further git pushing issues.  
If you already cloned it in Method 1, the following shows how to remove the original getting-started-todo-app

```bash
git rm --cached Implementation/getting-started-todo-app
rm -rf Implementation/getting-started-todo-app
```
Then use submodule to add the tutorial repository 
```bash
git submodule add https://github.com/docker/getting-started-todo-app Implementation/getting-started-todo-app
cd getting-started-todo-app
docker compose watch
```
If using VS Code or Cursor to run the above code on the remote server, you will find the docker has successfully ran but you can't open the GUI. This is due to the X-forwarding isssue between server and local computer
The follwing procedures show how to develope container in VS-Code-like environment
1. Install the **Dev Containers** extension (supposed you have installed
**Remote - SSH** extension and setup the ssh tunnel on your remote server)
2. Reopen the directory to getting-started-todo-app you installed 
3. Press `F1` or `Ctrl+Shift+P` to use the *Dev Containers: Reopen in Container* 

# Reference
https://docs.docker.com/get-started/introduction/develop-with-containers/
https://code.visualstudio.com/docs/remote/ssh
