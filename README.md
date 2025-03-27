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
        ansible-playbook -i inventories/000120003200 create_hosts_hostgroup_playbook.yml -e "debug_mode=true" --vault-password-file ~/.vp<br/>

2. Create Storage Group<br/>
  -- It creates a new storage group and adds newly created volumes to it (configureed in inventory file group_vars/create_storage_group/vars.yml)<br/>
  -- Run play book:<br/> 
        ansible-playbook -i inventories/000120003200 create_storage_group_playbook.yml -e "debug_mode=true" --vault-password-file ~/.vp<br/>

3. Create Volume<br/>
  -- It creates volume(s) and adds them to storage group (configureed in inventory file group_vars/create_volume/vars.yml)<br/>
  -- Run play book:<br/> 
        ansible-playbook -i inventories/000120003200 create_volume_playbook.yml -e "debug_mode=true" --vault-password-file ~/.vp<br/>

4. Create Port Group<br/>
  -- It creates a new port group and adds existing ports to it (configureed in inventory file group_vars/port_group/vars.yml)<br/>
  -- Run play book:<br/> 
        ansible-playbook -i inventories/000120003200 create_port_group_playbook.yml -e "debug_mode=true" --vault-password-file ~/.vp<br/>

5. Create Masking View<br/>
  -- It creates a new masking view with storage group, host group and port group (configureed in inventory file group_vars/create_maskingview/vars.yml)<br/>
  -- Run play book:<br/> 
        ansible-playbook -i inventories/000120003200 create_maskingview_playbook.yml -e "debug_mode=true" --vault-password-file ~/.vp<br/>

6. Create ESXi Host Datastore<br/>
  -- It creates ESXi host datastore after rescan (configureed in inventory file group_vars/create_esxi_host_datastore/vars.yml)<br/>
  -- Run play book:<br/> 
        ansible-playbook -i inventories/000120003200 create_esxi_host_datastore_playbook.yml -e "debug_mode=true" --vault-password-file ~/.vp<br/>

7. Add volume(s) and create ESXi Host Datastore<br/>
  -- It adds volume(s) to the storage group and then creates ESXi host datastore after rescan (configureed in inventory file group_vars/add_volume_datastore/vars.yml)<br/>
  -- Run play book:<br/> 
        ansible-playbook -i inventories/000120003200 add_volume_datastore_playbook.yml -e "debug_mode=true" --vault-password-file ~/.vp<br/>
