### IP 3 EXPLANATION FILE

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
