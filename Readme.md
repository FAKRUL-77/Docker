Docker Commands
- docker run ubuntu
- docker images/docker image ls
- docker ps/docker ps -a
- docker run -it ubuntu( to load ubuntu image into a container)
- docker container rm [docker_id] (to remove the docker iage)
- docker start -i [docker_id](to start the container)
- docker build -t 'tag name' 'directory name'( when we execute the build command docker client send the content of the directory to the docker engine)
- [tagging] docker build -t 'image-name':'tag-name' .
- [removing] docker image remove 'image-name':'tag-name'
- [tagging] docker image tag 'image-name':'current-tag' 'image-name':'new-tag'
- docker image rm 'image-id'
- docker container rm 'container-id'
- docker image prune
- docker container prune
- docker push 'image-name':'tag-name'
- docker image save --help
- docker image save -o 'the name of the file, where to save' 'image-name'
- docker image load --help

- docker run -d react-app
- docker run -d --name blue-sky react-app
- docker logs 'container-id'
- docker logs --help
- docker logs -n 'number of lines' 'container id'
- docker logs -n 'number of lines' -t 'container id'
- docker run -d -p 80:3000 --name 'any-name' 'image-name'

- [run-commands-on-running-container] docker exec 'container-name' 'commands'(docker exec c1 ls)
- docker exec -it c1 sh

- docker stop 'container-name'  
- docker start 'container-name'
- docker rm 'container-name'
- docker rm -f 'container-name'
- docker ps -a | grep 'container-name'

- [docker_volume] docker volume
- docker volume create app-data
- docker volume inspect app-data
- docker run -d -p 5000:3000 -v a---data:/app/data react-app

- [copy] docker cp c1:/app/log.txt(source) 'destination'

- docker run -d -p 5000:3000 -v $(pwd):/app react-app

Docker-compose:
- docker-compose up
- docker-compose up -d
- docker-compose up --build
- docker-compose ps
- docker-compose down
- docker-compose logs




Shell Commands(bash-born again shell)
- echo hello
- whoami(to show the current user)
- echo $0 (to see the location of the shell program)
- history(to show the history of command) -- (!1 or !2)
- apt list(to see all the packages)
- apt update(to update the package database)
- apt install nano(to install the nano package)
- apt remove nano(to remove the nano packag)
- ls
- pwd
- ls -1
- ls -l
- cd 'path name'
- cd ..
- ls 'path'
- cd ~
- mkdir 'directory name'(to create a directory)
- mv 'current dir name' 'new dir name'(to rename)
- touch 'file name'(to create a file like .txt)
- touch 'file 1 name' 'file 2 name' (to create multiple file at a time)
- rm 'file 1 name' 'file 2 name' 'file 3 name'(to remove files)
- rm file* (to remove all files at once, containing file..)
- rm -r 'directory name' (to delete recursively a directory and it's all files)
- nano file1.txt(to create a txt file and open a text editor).
- cat 'file name' (to see content of the file with short content, basically cat represent's concatenate)
- more 'file name' (to see content of the file)
- less 'file name' (to see content of the file)
- head -n 5 'file name' (to show first five line of a content),
- tail -n 5 'file name' (to show last five line of a content),
- cat 'resource file name' > 'destination file name'(to write the resource content into the destination)
- echo whatever > whatever.txt
- ls -l 'resource file path' > 'destination file name'
- grep -i hello file1.txt(to search hello into the file1.txt)
- grep -i hello file1.txt file2.txt(search in multiple file)
- grep -i hello file*(search in multiple file)
- grep -i -r 'string to search' 'directory name'( search in directory )
- grep -i -r 'string to search' .( search in directory )
- grep -ir 'string to search' 'directory name'( search in directory )
- find(finding all file and directory in the current directory)
- find -type d(find only directory in the current directory)
- find -type f -name "f*"(find all file which name start with f)
- find -type f -iname "F*"(find all file which name start with f)
- find /(directory name) -type f -iname "*.py" > python-files.txt(find the all the python file and white into python-file.txt)
- mkdir test; cd test; echo done(for chaining commands: if one command fails other commands will execute)
- mkdir test && cd test && echo done(if one command fails the other commands will not be executed)
- mkdir test || echo "directory already exists"(if the first command execute then the second command will not be executed but if first one not then second one will be executed)
- ls /bin | less, ls /bin head(what's comes out of 'ls /bin' commands goes into the second command)
- printenv(to see all environment variable)
- printenv PATH , echo $PATH
- export DB_USER=fakrul(to define a variable)

- echo DB_USER=fakrul >> .bashrc(to append something into .bashrc folder)
- source .bashrc(to relode .bashrc file)
- ps (to see all the running processes)
- sleep 3
- kill 'process id'
- useradd(for adding a user)
- usermod(for modifying a user)
- userdel(for deleting a user)
- groupadd 'groupname'
- usermod -G developers jhon(add a user into a group)
- 


Some Package Managers:
- npm
- yarn
- pip
- NuGet
- apt(advance package tool for ubuntu)

- [nano is a basic text editor for ubuntu]
- [using > we can redirect the standard output]
- [using < we can redirect the standard input]


Dockerfiel syntex:
- FROM (for specifying base image, base image can be an operating system or os + runtime environment, when we execute the build command docker client send the content of the directory to the docker engine).
    - FROM node:alpine  react-app .
- WORKDIR (for specifying the work directory).
- COPY
- ADD
- RUN (executing operating system commands)
- ENV (for setting environment variable)
- EXPOSE (for telling docker that our container is started on a given port).
- USER
- CMD
- ENTRYPOINT