**ElasticSearch Logstash Kibana installation

Now we have fully automated ansible playbook to create from scratch ELK stack.

For creation you need:

create inventory file with 3 sections [elk] - for elasticsearch servers [elk-kibana] - for kibana servers [elk-logstash] - for logstash servers ElasticSearch support recommended use for elasticsearch and kibana same servers. Logstash servers can use other servers.

create group_vars/elk.yml file with parameters: elk.user: ElasticSearch user es_port: ElasticSearch port es_cluster: ElasticSearch cluster name es_elb_name: ElasticSearch ELB name/DNS alias xpack_enable: For enabling/disabling ElasticSearch security kibana_port: Kibana port logstash_docker_port: Logstash listen port for docker input logstash_beats_port: Logstash listen port for beats input logstash_docker_elb: Logstash ELB name/DNS alias

To create ELK from ansible playlist you will run command:

ansible-playlist -i elk.yml --vault-password-file ~/.ssh/vault.txt
