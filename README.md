This is reference implementation for Dell PowerMax automation. The usecases are:
- Create Storage Group<br/>
  -- It creates a new storage group and adds newly created volumes to it (configureed in inventory file group_vars/create_storage_group/vars.yml)<br/>
  -- Run play book:<br/> 
        ansible-playbook -i inventories/000220002205 create_storage_group.yml --vault-password-file ~/.vp -e "debug_mode=true"<br/>

- Create Port Group<br/>
  -- It creates a new port group and adds existing ports to it (configureed in inventory file group_vars/port_group/vars.yml)<br/>
  -- Run play book:<br/> 
        ansible-playbook -i inventories/000220002205 create_port_group.yml --vault-password-file ~/.vp -e "debug_mode=true"<br/>
