# Cluster MySQL

## Équipe

- FEUGERE Thibault
- LIJOUR Udo

## Choix technologique

Comme il l'était recommandé, nous sommes parti sur Vagrant malgré une hésitation avec Docker et son orchestrateur docker-compose.

L'hyperviseur choisit est VirtualBox.

## Configuration de VirtualBox

Bien que Vagrant automatise de nombreuses tâches, la plage d'adresse IP nécessaire doit être changé au préalable pour éviter l'erreur : 

```
The IP address configured for the host-only network is not within the
allowed ranges. Please update the address used to be within the allowed
ranges and run the command again.

  Address: 10.0.0.11
  Ranges: 192.168.56.0/21

Valid ranges can be modified in the /etc/vbox/networks.conf file. For
more information including valid format see:

  https://www.virtualbox.org/manual/ch06.html#network_hostonly
``` 

On y apprend : `On Linux, Mac OS X and Solaris Oracle VM VirtualBox will only allow IP addresses in 192.168.56.0/21 range to be assigned to host-only adapters. For IPv6 only link-local addresses are allowed. If other ranges are desired, they can be enabled by creating /etc/vbox/networks.conf and specifying allowed ranges there.`.

Cela nous concerne puisque nous sommes sur MacOs, nous avons donc créé le fichier `/etc/vbox/networks.conf` et ajouté cette ligne :

`* 10.0.0.0/24`

