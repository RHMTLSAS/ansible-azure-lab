ANSIBLE-PLAYBOOK = ansible-playbook
ANSIBLE-GALAXY = ansible-galaxy


.PHONY:
all: requirements

%: %.yml
	$(ANSIBLE-PLAYBOOK) $*.yml
	@if [ -a $*.retry ]; \
	then \
		rm $*.retry ; \
	fi;  

.PHONY:
requirements:
	ANSIBLE-GALAXY install -r roles/requirements.yml -p ./roles/ --force

.PHONY:
clean:
	rm *.retry
