# Zabbix sensors

Repo with scripts for auto discovery sensors at Zabbix Agent and templates for auto creating elements, triggers, graphs at Zabbix Server.

Now in repo only packages for auto discovery at Zabbix Agent and auto creating at Zabbix Server all **lm-sensors**

# Getting started

## Debian/Ubuntu

Connect repository to apt by commands:

    wget -O - https://dimdim1177.github.io/zabbix-sensors/gpg.key | sudo apt-key add -
    echo "deb https://dimdim1177.github.io/zabbix-sensors $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/zabbix-sensors.list
    apt update

### Zabbix Agent side

Install package 

    apt install zabbix-agent-lm-sensors

### Zabbix Server side

Install package

    apt install zabbix-agent-lm-sensors
    
Then import one of template "Template LM Sensors*.xml" from /usr/share/zabbix-server-lm-sensors/

## Manual install

### Zabbix Agent side

Download and extract latest package files

    wget https://dimdim1177.github.io/zabbix-sensors/tar/zabbix-agent-lm-sensors_latest.tar.gz
    tar xf zabbix-agent-lm-sensors_latest.tar.gz
    
Then copy zabbix-agent-lm-sensors in some system bin directory, for example

    cp zabbix-agent-lm-sensors /usr/bin/
    
Then install config file for Zabbix Agent

    zabbix-agent-lm-sensors config en > /etc/zabbix/zabbix_agentd.d/userparameter_lm_sensors.conf

Where 'en' is English language of sensor names.
You can select some other language: fr - French, de - German, es - Spanish, it - Italian, ru - Russian.  
    
Then restart Zabbix Agent

### Zabbix Server side

Download and extract latest package files

    wget https://dimdim1177.github.io/zabbix-sensors/tar/zabbix-server-lm-sensors_latest.tar.gz
    tar xf zabbix-server-lm-sensors_latest.tar.gz
    
Then import one of template "Template LM Sensors*.xml" from folder extracted folder
