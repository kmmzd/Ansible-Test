# Ansible-Test
ansible sample tenplate.  
Ansibleのサンプルリポジトリです。  
Ec2インスタンスを対象にしています。  
対象インスタンスのipアドレスは、動的インベントリプラグインを用いて、インスタンスの`EnvType`タグから取得します。  
実行内容は、git,mysql,nginx,nodejs,railsのインストールとなります。

https://docs.ansible.com/ansible/latest/collections/amazon/aws/aws_ec2_inventory.html


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

# hosts/aws_ec2.yml
aws_ec2インベントリプラグインを用い、ipアドレスを取得する設定を記述しています。  
具体的には、`EnvType`タグを値`dev`,`prod`にグループ分けし、各グループごとのipアドレスを取得します。

# roles
具体的な設定内容を各main.ymlに記述しています。  
rubyのみ、jinja2テンプレートを利用しています。

# ansible.cfg  
SSH接続、インベントリファイルのパスの設定を記述しています。

# playbook.yml
hostsグループの指定、変数、実行ロールを記述しています。
