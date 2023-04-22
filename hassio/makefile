IP ?= $(shell ifconfig | grep -Eo 'inet (addr:)?([0-9]*\.){3}[0-9]*' | grep -Eo '([0-9]*\.){3}[0-9]*' | grep -v '127.0.0.1' | grep ^192 | head -1)

#------------------------------------------------------------------------------

run:
	$(MAKE) ip_set
	docker-compose up -d

#------------------------------------------------------------------------------

stop:
	docker-compose down
	$(MAKE) ip_rev

#------------------------------------------------------------------------------

permissions:
	@echo Setting permissions
	sudo chown -R ${USER}:${USER} data
	sudo chown -R 472:472 ./data/grafana
	@echo Done

#------------------------------------------------------------------------------

ip_set:
	@echo Setting IP from localhost to ${IP}
	sed -i "s/localhost/${IP}/g" data/homeassistant/config/configuration.yaml
	@echo Done

#------------------------------------------------------------------------------

ip_rev:
	@echo Setting IP from ${IP} to localhost
	sed -i "s/${IP}/localhost/g" data/homeassistant/config/configuration.yaml
	@echo Done

#------------------------------------------------------------------------------

backup-make:
	@echo Making a backup
	sudo rm -rf data.bak
	sudo cp -r data data.bak
	@echo Done

#------------------------------------------------------------------------------

backup-restore:
	@echo Restoring a backup
	$(MAKE) clean
	sudo cp -r data.bak data
	$(MAKE) permissions
	@echo Done

#------------------------------------------------------------------------------

clean:
	@echo Cleaning
	sudo rm -rf data
	@echo Done

#------------------------------------------------------------------------------

clean-all:
	@echo Cleaning all
	$(MAKE) clean
	sudo rm -rf data.bak
	@echo Done

#------------------------------------------------------------------------------

help:
	@echo "Parameters:"
	@echo "  IP (IP)        - host's IP address"
	@echo ""
	@echo "Targets"
	@echo "  run            - set host's IP address and run containers"
	@echo "  stop           - stop containers and restore default IP address"
	@echo "  permissions    - set correct permissions in data folder"
	@echo "  ip_set         - set host's IP address"
	@echo "  ip_rev         - restore default IP address"
	@echo "  backup-make    - make a backup"
	@echo "  backup-restore - restore a backup"
	@echo "  clean          - delete ./data directory"
	@echo "  clean-all      - delete ./data and ./data.bak directories"
