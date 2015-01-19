# puppet
configuration du serveur puppet

installation 
wget http://apt.puppetlabs.com/puppetlabs-release-stable.deb
dpkg -i puppetlabs-release-stable.deb
aptitude update
aptitude install puppetmaster

==> Le distributeur du paquet a fourni une version mise à jour.
   Que voulez-vous faire ? Vos options sont les suivantes :
    Y ou I  : installer la version du responsable du paquet
    N ou O  : garder votre version actuellement installée
      D     : afficher les différences entre les versions
      Z     : suspendre ce processus pour examiner la situation
 L'action par défaut garde votre version actuelle.
*** puppet.conf (Y/I/N/O/D/Z) [défaut=N] ? y

vi /etc/default/puppetmaster
==> mettez START=no

/etc/init.d/puppetmaster stop
aptitude install puppetmaster-passenger
aptitude install nginx mongrel

vi /etc/default/puppetmaster
START=yes
DAEMON_OPTS=""
PORT=8140
SERVERTYPE=mongrel
PUPPETMASTERS=4
