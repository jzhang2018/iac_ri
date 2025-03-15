This is reference implementation for Dell PowerMax automation. 

Prerequisites:<br/>
- python3 - install PyU4V==10.1.0.0<br/>
- ansible-galaxy collection install dellemc.powermax<br/>
- python3 -m pip install pyvmomi<br/>
- ansible-galaxy collection install community.vmware --upgrade --ignore-cert<br/>

The usecases are:<br/>
1. Create Hosts and Host Group<br/>
  -- It creates a new host group and adds hosts to it (configureed in inventory file group_vars/create_hosts_hostgroup/vars.yml)<br/>
  -- Run play book:<br/> 
        ansible-playbook -i inventories/000120003200 create_hosts_hostgroup_playbook.yml --vault-password-file ~/.vp -e "debug_mode=true"<br/>

2. Create Storage Group<br/>
  -- It creates a new storage group and adds newly created volumes to it (configureed in inventory file group_vars/create_storage_group/vars.yml)<br/>
  -- Run play book:<br/> 
        ansible-playbook -i inventories/000120003200 create_storage_group_playbook.yml --vault-password-file ~/.vp -e "debug_mode=true"<br/>

3. Create Port Group<br/>
  -- It creates a new port group and adds existing ports to it (configureed in inventory file group_vars/port_group/vars.yml)<br/>
  -- Run play book:<br/> 
        ansible-playbook -i inventories/000120003200 create_port_group_playbook.yml --vault-password-file ~/.vp -e "debug_mode=true"<br/>

4. Create Masking View<br/>
  -- It creates a new masking view with storage group, host group and port group (configureed in inventory file group_vars/create_maskingview/vars.yml)<br/>
  -- Run play book:<br/> 
        ansible-playbook -i inventories/000120003200 create_maskingview_playbook.yml --vault-password-file ~/.vp -e "debug_mode=true"<br/>
