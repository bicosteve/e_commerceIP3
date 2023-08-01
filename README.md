### PROJECT README

#### 1. Inventory:

    My inventory is located in the inventory folder where the hosts file contains ansible host and ansible port. The host is 127.0.0.1 and the port is 2222.

#### 2. Config File.

    My config file rests in the root directory of the project on ansible.cfg.  It has inventory, remote user, private_key_file, playbook and host key checking set to False. The host key being false will prevent being asked for access key when we run ansible playbook. In addition, I have stated inventory plugins allowed for the hosts file which are the file extensions for the hosts file.

#### 3. Roles

    The roles are divided into aptitude, compose, docker, git, pip, repo.
    1. Aptitude -> this role has tasks to install apt packages to ubuntu marchine.
    2. Compose -> this role is assigned tasks to run docker compose up -d to build and run our containers.
    3. Docker -> this role has tasks that will download and install docker and docker compose CE in the virtual marchine.
    4. Git -> this role has task to install git version control on virtual marchine.
    5. Pip -> this role has task to install and update pip3 packages for python3 on the virtual marchine.
    6. Repo -> this role has tasks to clone our e_commerceIP2 repo from Github, create directory and clone it in the created directory.

#### 4. Block

    I have included block on the roles which have more than one task to group the task.

#### 5. Playbook.yml

    The playbook contains hosts, remote_user, become, and become_user.
    1. Hosts is set to all for this project but it can be grouped according to the hosts set on the hosts file.
    2. Remote_User is set to vagrant to give access to our virtual marchine and perfome functions there as the root user.
    3. Become_user is set to root which give the vagrant user all the root previledges.
    4. The playbook tasks have been added to their various roles therefore breaking the playbook in parts. Each task has been listed on the playbook with its role.

#### 6. Running provisioning remote server

    Use vagrant up to provision the server.
    You can also clone the repo and navigate to the dir in your command line. Run ansible-playbook -i ./inventory/hosts playbook.yml. This will provision the server and start the container.

#### 7. Vagrantfile

     The file has port mappings for accessibility outside the virtual machine where the server is 5000, client is 3000 and the mongodb is 27017. To access the client, run http://localhost:3000 on your browser to launch client application.  You can also access the backend service by runninng http://localhost:5000/api/products on Postman or Insomnia to access the API.

#### 8. Running the containers

     To run the containers with ansible playbook, we will use 'ansible-playbook -1 ./inventory/hosts playbook.yml --tags docker-compose'
     I have added the --tags flag to avoid running other tasks but just the docker-compose task which has a tag name of 'docker-compose'

#### 9. Localhost Running Version of the app

    To view how the application is running on our virtual marchine, this is the link of the video https://www.awesomescreenshot.com/video/19573677?key=1705827d63cc8ccf054231b0d9d414d2
