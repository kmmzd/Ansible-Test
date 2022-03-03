# Ansible-Test
ansible sample tenplate.  
Ansibleのサンプルリポジトリです。 

# Diagram
```
ansible-test
├── hosts
│   └── aws_ec2.yml   
├── roles
|   ├── git/tasks
|   |   └── main.yml
|   ├── mysql/tasks
|   |   └── main.yml
|   ├── nginx/tasks
|   |   └── main.yml
|   ├── nodejs/tasks
|   |   └── main.yml
|   └── ruby
|       ├── tasks
|       |   └── main.yml
|       └── templates
|           └── rbenv_system.sh.j2
├── ansible.cfg
└── playbook.yml
```
