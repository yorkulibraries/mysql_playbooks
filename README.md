# mysql_playbooks
A collection of playbooks to automate mysql tasks

## Installation
```
ansible-galaxy install -r requirements.yml
```

### Dump a database
The following will dump database name foo_db to /tmp/foo_db.sql
```
ansible-playbook -i inventory dump.yml  -e "db=foo_db"
```

### Import a database
Assume you have dumped the database foo_db using the playbook above. You can then import that database using the playbook below.

The following will import database foo_db from the /tmp/foo_db.sql into the bar_db on the server **demos**
```
ansible-playbook -i inventory import.yml  -e "from_db=foo_db to_db=bar_db" --limit demos
```
