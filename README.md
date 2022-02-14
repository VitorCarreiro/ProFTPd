# ProFTPd Config for EC2 / RedHat

**You need to install the epel package to be able to install proftpd** ➡️ *yum install epel-release*

**Install proftpd** ➡️ *yum install proftpd*

**Create certificates and place them here** ✔️

➡️ `/etc/ssl/certs/cert.crt*

➡️ */etc/ssl/certs/key.key*`

**Go to the config file /etc/proftpd.conf**

**Add the ports you want to use for your passive ftp, you can place it on the last line** ✔️

➡️ `PassivePorts    10000    10100`

**Comment these lines** ⬇️

         # <IfDefine TLS>
         #  <IfModule mod_tls_shmcache.c>
         #    TLSSessionCache            shm:/file=/var/run/proftpd/sesscache
         #  </IfModule>
         #</IfDefine>
         
**Change your cert and key to where you placed them** ✔️

➡️ `TLSRSACertificateFile         /etc/ssl/certs/cert.crt

➡️ TLSRSACertificateKeyFile      /etc/ssl/private/key.key`

**Create a user if you need to** ✔️

➡️ `adduser client`

**Now that everything is ready start the server** ✔️

➡️ `systemctl enable --now proftpd`
