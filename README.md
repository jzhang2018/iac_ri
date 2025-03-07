This is reference implementation for Dell PowerMax automation. 

Prerequisites:<br/>
- python3 - install PyU4V==10.1.0.0<br/>
- ansible-galaxy collection install dellemc.powermax<br/>
- python3 -m pip install pyvmomi<br/>
- ansible-galaxy collection install community.vmware --upgrade --ignore-cert<br/>

The usecases are:<br/>

1. Gather VCenter ESXi Host Info<br/>
  -- It gathers vcenter esxi host details for those type is 'fibre Channel' and the status is online(configureed in inventory file group_vars/gather_vcenter_cluster_info/vars.yml)<br/>
  -- Run play book:<br/> 
        ansible-playbook -i inventories/000120003200 gather_vcenter_cluster_info.yml --vault-password-file ~/.vp -e "debug_mode=true"<br/>

2. Create Hosts and Host Group<br/>
  -- It creates a new host group and adds hosts to it (configureed in inventory file group_vars/create_hosts_hostgroup/vars.yml)<br/>
  -- Run play book:<br/> 
        ansible-playbook -i inventories/000120003200 create_hosts_hostgroup.yml --vault-password-file ~/.vp -e "debug_mode=true"<br/>

3. Create Storage Group<br/>
  -- It creates a new storage group and adds newly created volumes to it (configureed in inventory file group_vars/create_storage_group/vars.yml)<br/>
  -- Run play book:<br/> 
        ansible-playbook -i inventories/000120003200 create_storage_group.yml --vault-password-file ~/.vp -e "debug_mode=true"<br/>

4. Create Port Group<br/>
  -- It creates a new port group and adds existing ports to it (configureed in inventory file group_vars/port_group/vars.yml)<br/>
  -- Run play book:<br/> 
        ansible-playbook -i inventories/000120003200 create_port_group.yml --vault-password-file ~/.vp -e "debug_mode=true"<br/>
