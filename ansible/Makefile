all: ansible

lint:
	ansible-lint playbook.yml

ansible: lint
	ansible-playbook -i host.ini playbook.yml
