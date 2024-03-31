ANSIBLE : [Assignmet 2 Ansible Wiki Page](https://github.com/cybermad7373/73772126145-DevOps-Assignment2/wiki/Ansible)

DOCKER : [Assignmet 2 Docker Wiki Page](https://github.com/cybermad7373/73772126145-DevOps-Assignment2/wiki/Docker)



**Ansible Guide**

Ansible is a powerful automation tool for configuration management, application deployment, and task automation. Ansible uses simple, human-readable YAML syntax and requires no agents to be installed on managed nodes.

**1. Installation:**

Ensure you have Ansible installed on your control node. You can install Ansible via package managers like yum or apt, or using Python's pip package manager:

```bash
# On Debian/Ubuntu
sudo apt-get update
sudo apt-get install ansible

# On RHEL/CentOS
sudo yum install ansible

# Using pip
sudo pip install ansible
```

**2. Inventory:**

An Ansible inventory file is a simple INI file or YAML file where you define your managed hosts. By default, Ansible looks for an inventory file at `/etc/ansible/hosts`, but you can specify a custom inventory file using the `-i` option.

Example `inventory.ini` file:

```ini
[web]
webserver1.example.com
webserver2.example.com

[db]
dbserver.example.com
```

**3. Configuration:**

Ansible uses a configuration file, `ansible.cfg`, to define settings such as the location of the inventory file, SSH keys, and other options. You can create a global `ansible.cfg` in `/etc/ansible/` or use a local `ansible.cfg` in your project directory.

Example `ansible.cfg`:

```ini
[defaults]
inventory = /path/to/your/inventory.ini
remote_user = your_ssh_user
private_key_file = /path/to/your/private_key
```

**4. Playbooks:**

Ansible playbooks are YAML files that define a set of tasks to be executed on managed hosts. Each task is a call to an Ansible module. Playbooks can be used for configuration management, application deployment, and orchestration.

Example `playbook.yml`:

```yaml
---
- name: Install Nginx
  hosts: web
  tasks:
    - name: Install Nginx
      apt:
        name: nginx
        state: present
      become: yes
```

**5. Running Playbooks:**

You can execute playbooks using the `ansible-playbook` command:

```bash
ansible-playbook playbook.yml
```

**6. Ad-hoc Commands:**

In addition to playbooks, Ansible allows you to execute ad-hoc commands on managed hosts using the `ansible` command. For example, to ping all hosts:

```bash
ansible all -m ping
```

**7. Requirements:**

Before getting started, ensure you have:

- Access to the systems you intend to manage with Ansible.
- Proper SSH connectivity to managed hosts (with necessary permissions).
- Basic understanding of YAML syntax for writing playbooks.
- Optional: Familiarity with Linux/Unix systems administration.

**8. Further Learning:**

- Official Ansible Documentation: [https://docs.ansible.com/ansible/latest/index.html](https://docs.ansible.com/ansible/latest/index.html)
- Ansible Galaxy for sharing roles: [https://galaxy.ansible.com/](https://galaxy.ansible.com/)
- Ansible Community: [https://community.ansible.com/](https://community.ansible.com/)



**Docker Guide**

Docker is a platform for developing, shipping, and running applications inside containers. Containers allow you to package your application and its dependencies into a standardized unit for software development. This guide will help you get started with Docker on both Windows and Linux.

**1. Installation:**

- **For Linux:**

    Docker installation on Linux varies based on your distribution. Below are general steps for Ubuntu/Debian and CentOS/RHEL:

    ```bash
    # Update package index
    sudo apt-get update
    
    # Install dependencies
    sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
    
    # Add Docker's official GPG key
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
    
    # Add Docker repository
    sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
    
    # Install Docker
    sudo apt-get update
    sudo apt-get install docker-ce
    ```

- **For Windows:**

    Docker Desktop is the preferred way to install Docker on Windows. You can download it from the official Docker website and follow the installation instructions provided.

**2. Verification:**

After installation, verify that Docker is running by executing:

```bash
docker --version
docker run hello-world
```

If Docker is installed correctly, you'll see a welcome message confirming the installation.

**3. Docker Basics:**

- **Images:** Docker images are read-only templates used to create containers. You can pull images from Docker Hub or create your own.

- **Containers:** Containers are instances of Docker images. They run applications in isolated environments.

- **Dockerfile:** Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image.

**4. Docker on Windows:**

- **Windows Containers:** Docker on Windows supports both Windows and Linux containers. Windows containers use Windows Server Core or Nano Server as a base image.

- **Docker Desktop:** Docker Desktop for Windows provides an easy-to-use interface to manage Docker containers and images on Windows.

**5. Docker Compose:**

Docker Compose is a tool for defining and running multi-container Docker applications. It uses a YAML file to configure application services and their dependencies.

**6. Docker Swarm (Optional):**

Docker Swarm is Docker's native clustering and orchestration tool. It allows you to create and manage a cluster of Docker nodes.

**7. Further Learning:**

- Official Docker Documentation: [https://docs.docker.com/](https://docs.docker.com/)
- Docker Hub: [https://hub.docker.com/](https://hub.docker.com/)
- Docker Community Forums: [https://forums.docker.com/](https://forums.docker.com/)
