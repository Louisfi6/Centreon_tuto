# Centreon_tuto

- je fais le plan d'adressage
	Zone réseau 1 : 192.168.1.1
		WindowsServer : 192.168.1.2
		CentraleAlma : 192.168.1.3
	Zone réseau 2 : 192.168.2.1
		Debian : 192.168.2.2
		CollecteurAlma : 192.168.2.3
- je up mes iso avec mes machines
- je configure les cartes réseau : NAT / ADM / CLT
- je mets les machines sur leur zone réseau
- je configure opnsense tout en ejectant le disque virtuel lors du reboot
- je me connecte en tant que root
- je vais aller dans assign interfaces
- je vais aller set les interfaces IP
- je configure le dns adds smtp sur le windows server
- je mets mon ip static sur windows, linux et les  alma
- je désactive windows defender sinon pas de ping
- je commence à configurer mon central sur : https://docs.centreon.com/fr/docs/installation/installation-of-a-central-server/using-packages/
- une fois fait je suis la démarche sur : https://docs.centreon.com/fr/docs/installation/web-and-post-installation/#web-
- le mdp de centreon sera : <pass>
- je configure mon collecteur sur : https://docs.centreon.com/fr/docs/installation/installation-of-a-poller/using-packages/
- une fois que cela est dait je rajoute mon collecteur dans l'interface de centreon avec : https://docs.centreon.com/fr/docs/monitoring/monitoring-servers/add-a-poller-to-configuration/
- il faut faire un wget du pastebin dans lequel on a copié collé le gorgoned
- si tout est ok alors on supervise notre premiere ressource via : https://docs.centreon.com/fr/docs/getting-started/monitor-windows-server-with-snmp/
- ensuite on peut superviser un linux avec : https://docs.centreon.com/fr/docs/getting-started/monitor-linux-server-with-snmp/
- il faut installer le snmpd sur le linux car il n'est pas installé par défaut
- il faut tout supprimer dans snmpd.conf et mettre que rocommunity <com> <ip>
- on peut superviser le opnsense
- Page web administrateur OPNsense -> system -> firmware ->         	plugins -> os-net-snmp(+ pour l'installation)-> 	services -> NET-SNMP :
	Enable SNMP Service : ✅ 
	SNMP Community : "nom de la communauté
	Layer 3 Visibility : ✅ 
	Listen IPs : "l'ip d'OPNsense
- si tout est bon on peut mettre la sonde avec https://agbodja.blog/2020/06/14/superviser-une-machine-linux-avec-nrpe-et-centreon/ (problème avec le ssl)
