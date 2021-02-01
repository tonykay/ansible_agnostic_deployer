GUID=00
OSP_CLUSTER=orange

deploy:
	ansible-playbook main.yml \
		-e @configs/ansible-multitier-infra/sample_vars/multitier_app_with_tower.yml \
		-e@~/secrets/openstack-red-secret.yml \
		-e@~/secrets/yum-server.yml \
		-e guid=multi-$(GUID)

destroy:
	ansible-playbook destroy.yml \
		-e @configs/ansible-multitier-infra/sample_vars/multitier_app_with_tower.yml \
		-e@~/secrets/openstack-red-secret.yml \
		-e guid=multi-$(GUID)

# Podman configs incluse a utility server

deploy-podman:
	ansible-playbook main.yml \
		-e @configs/ansible-multitier-infra/sample_vars/multitier_podman_rhel_7.yml \
		-e@~/secrets/openstack-red-secret.yml \
		-e@~/secrets/yum-server.yml \
		-e guid=multi-podman-$(GUID)

destroy-podman:
	ansible-playbook destroy.yml \
		-e @configs/ansible-multitier-infra/sample_vars/multitier_podman_rhel_7.yml \
		-e@~/secrets/openstack-red-secret.yml \
		-e@~/secrets/yum-server.yml \
		-e guid=multi-podman-$(GUID)

# Utility a PoC config validating the use of padman v docker for local utility containers

deploy-utility:
	ansible-playbook main.yml \
		-e @configs/ansible-multitier-infra/sample_vars/multitier_utility_rhel_8.yml \
		-e@~/secrets/openstack-orange-secret.yml \
 		-e@~/secrets/ansible-advanced-satellite-secret.yml \
		-e guid=multi-utility-$(GUID)
		

destroy-utility:
	ansible-playbook destroy.yml \
		-e @configs/ansible-multitier-infra/sample_vars/multitier_utility_rhel_8.yml \
		-e@~/secrets/openstack-orange-secret.yml \
 		-e@~/secrets/ansible-advanced-satellite-secret.yml \
		-e guid=multi-utility-$(GUID)

