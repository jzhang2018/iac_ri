This is reference implementation for Dell PowerMax automation. The usecases are:
- Provision Cluster. The work flow is: create storage group -> create volumes -> create host(s) -> create host group(s) -> create port group -> Create MV with existing elements
- The configuration is under inventories. The values are from my personal lab so make sure you will need to make necessary changes
- To run the playbook:
  1) ansible-playbook -i inventories/dev provision_cluster.yml --vault-password-file ~/.vp
  2) if you need ti turn on debug message, run: ansible-playbook -i inventories/dev provision_cluster.yml --vault-password-file ~/.vp -e "debug_mode=true"
  3) if you want to run it on different array, run: ansible-playbook -i inventories/dev provision_cluster.yml --vault-password-file ~/.vp -e "serial_no='000220002206'"  
