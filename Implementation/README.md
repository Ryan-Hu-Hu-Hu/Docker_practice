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
If using VS Code or Cursor to run the above code on the remote server, you will find the docker has successfully ran but you can't open the GUI. This is due to the porting isssue between server and local computer
The follwing procedures show how to develope container in VS-Code-like environment
1. Install the **Dev Containers** extension (supposed you have installed
**Remote - SSH** extension and setup the ssh tunnel on your remote server)
2. Reopen the directory to getting-started-todo-app you installed 
3. Press `F1` or `Ctrl+Shift+P` to use the *Dev Containers: Reopen in Container*. It may take some time to setup the container server for the first opening.
4. Check the ports number in compose.yml of your image (Ex: 80:80, the former 80 is the docker port and the latter is the remote setver machine)
5. Use `ssh -L LOCAL_PORT_TO_SET:localhost:REMOTE_PORT_FROM_REMOTE_MACHINE user@remote-server-ip`. In my case is `ssh -L 80:localhost:80 xxx@xxx` because I use default setting in docker 
6. Open `http://localhost:LOCAL_PORT_TO_SET` in your browser, in my case is `http://localhost:80`
7. You can see the beautiful frontend interface on your browser!


# Reference
1.https://docs.docker.com/get-started/introduction/develop-with-containers/
2.https://code.visualstudio.com/docs/remote/ssh
