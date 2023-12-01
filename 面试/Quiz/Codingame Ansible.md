
# QCM

### Control node Windows
Language knowledge (20 pts)

Can Ansible (control node) be installed on a Windows operating system?

- Yes
- Yes but only after installing Python on Windows
- No

### no_log attribute
Language knowledge (40 pts)

You have a task for which you do not want to display the executed command or the command results even when the playbook is executed in verbose mode `-v`.

Which of the following attributes can be useful?

```yaml
- name: Dont show sensitive information
  shell: /usr/bin/command --value={{ sensitive_info }}
  Your_answer_goes_here
```

- no_log: False
- log: False
- debug : False
- no_log: True

### Tags
Language knowledge (40 pts)

What is the purpose of **tags** in ansible?

_Select all that apply._

- To label resources in Ansible
- To run a specific part of a playbook
- To skip specific parts of a playbook
- They do nothing and exist for informational purposes

### Variable naming
Language knowledge (40 pts)

Which of the following **Ansible variable** names are **valid**?

_Multiple answers expected._

- Myvar123
- 123myvar
- myvar-123
- myvar_123

### start-at-task
Language knowledge (40 pts)

If you want to **begin executing** your playbook at a **particular task**, which command line parameter should be used?

- `--start-at-step`
- `--start-at-task`
- `--step`
- `--tags`

### EC2 provisionning
Language knowledge (20 pts)

Which Ansible module can be used to provision **EC2 instances** in Amazon Web Services?

- boto3
- aws
- ec2
- cloud

### Ansible Tower
Language knowledge (20 pts)

What is Ansible Tower?

- It is a version control tool for ansible playbooks.
- It is a web console and REST API for operating Ansible across teams/organizations.
- It is command line tool for running ansible commands.
- It is a platform where ansible developers share playbooks.

### Ansible in Python
Language knowledge (20 pts)

In which **programming language** is ansible primarily written in?

- Java
- Python
- C++
- Golang
- Bash
- NodeJS

### Ansible Vault
Language knowledge (20 pts)

Which Ansible feature can be used to **store and manage your credentials** in an encrypted file?

- ansible-key
- ansible-encrypt
- ansible-vault
- ansible-password

### Become User
Language knowledge (20 pts)

Under which user will the command be executed remotely when using the code below in your playbook?

```yaml
- name: Run some command 
  command: Random Command 
  become: yes 
  become_user: postgres
```

- Postgres
- root
- The command will not execute because Postgres is not root
- Ansible

### jinja2
Language knowledge (20 pts)

Which **templating** solution is used by Ansible?

- yaml
- html
- jinja2
- jade
