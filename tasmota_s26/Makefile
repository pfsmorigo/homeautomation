SHELL := /bin/bash # In order to run source command

VIRTUALENV := venv
PORT := /dev/ttyUSB0
COMMAND := esptool.py -p ${PORT}

BACKUP_FILE := backup_$(shell date --iso=seconds).bin

default:
	@echo "Options: install_esmtool backup"

install_esmtool: ${VIRTUALENV}
	source ${VIRTUALENV}/bin/activate; \
		pip3 install esptool

backup:
	source ${VIRTUALENV}/bin/activate; \
		${COMMAND} read_flash 0x00000 0x100000 ${BACKUP_FILE}

${VIRTUALENV}:
	virtualenv -p python3 ${VIRTUALENV}

clean:
	${RM} -r backup_*.bin

dist-clean: clean
	${RM} -r ${VIRTUALENV}
