This is reference implementation for Dell PowerMax automation. The usecases are:
- Create Storage Group<br/>
  -- It creates a new storage group and adds existing volumes to it (configureed in inventory file group_vars/storage_group/vars.yml)<br/>
  -- Run play book:<br/> 
        ansible-playbook -i inventories/000220002205 storage_group.yml --vault-password-file ~/.vp -e "debug_mode=true state=present"<br/>

- Remove Storage Group<br/>
  -- It removes volumes from the storage group and then deletes the storage group (configureed in inventory file group_vars/storage_group/vars.yml)<br/>
  -- Run play book:<br/> 
        ansible-playbook -i inventories/000220002205 storage_group.yml --vault-password-file ~/.vp -e "debug_mode=true state=absent"<br/>

- Create Port Group<br/>
  -- It creates a new port group and adds existing ports to it (configureed in inventory file group_vars/port_group/vars.yml)<br/>
  -- Run play book:<br/> 
        ansible-playbook -i inventories/000220002205 port_group.yml --vault-password-file ~/.vp -e "debug_mode=true state=present"<br/>

- Remove Port Group<br/>
  -- It removes ports from the port roup and then deletes the port group (configureed in inventory file group_vars/storage_group/vars.yml)<br/>
  -- Run play book:<br/> 
        ansible-playbook -i inventories/000220002205 port_group.yml --vault-password-file ~/.vp -e "debug_mode=true state=present"