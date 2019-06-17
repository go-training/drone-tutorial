all: ansible

lint:
	ansible-lint --exclude=$(HOME)/.ansible/roles playbook.yml

ansible: lint
	ansible-playbook -i host.ini playbook.yml
