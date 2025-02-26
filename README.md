This is reference implementation for Dell PowerMax automation. The usecases are:
- Provision Cluster. The work flow is: create storage group -> create volumes -> create host(s) -> create host group(s) -> create port group -> Create MV with existing elements
- The configuration is under inventories. The values are from my personal lab so make sure you will need to make necessary changes
- To run the playbook:
  1) ansible-playbook -i inventories/000220002205 provision_cluster.yml --vault-password-file ~/.vp
    Here '000220002205' is the cluster/array id/name. The configurations under that directory is for that cluster/array only.
  2) if you need ti turn on debug message, run: ansible-playbook -i inventories/000220002205 provision_cluster.yml --vault-password-file ~/.vp -e "debug_mode=true"

