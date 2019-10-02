## Security role

Some description for Security role would be nice. Any volunteers?
  
Read more about Ansible's User module [here](https://docs.ansible.com/ansible/latest/modules/user_module.html).

Read more about Ansible's File module [here](https://docs.ansible.com/ansible/latest/modules/file_module.html).

### Parameters

**security_users** (type `array`, default `[]`)

Example:
```yaml
security_users:
    # Create user 'hello' with password 'world' and create home directory
    - name: hello
      password: world
      shell: /bin/bash
      home: yes

    # Add user 'hello' to 'www-data' group
    - name: hello
      groups:
        - www-data

    # Update password for user 'hello'
    - name: hello
      password: people
      password_change: yes

    # Remove user 'hello' and also delete it's home directory
    - name: hello
      remove: yes
    
    # Create user 'myuser' and disable login
    - name: myuser
      shell: /usr/sbin/nologin
```

**security_files** (type `array`, default `[]`)

Example:
```yaml
security_files:
    # Change the owner
    - path: /var/www/website
      user: hello

    # Change the owner and group including subdirectories
    - path: /var/www/website
      user: hello
      group: hello
      recurse: yes

    # Create directory
    - path: /var/www/website
      create: yes
```
