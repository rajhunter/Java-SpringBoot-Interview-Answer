**[Cd /etc/jitsi/meet/ ...config file]{.mark}**

Cd /usr/share some configurations file / jitsi or jocofo

hosts: {

// XMPP domain.

domain:\'raj-openfire.magnet.com\',

// XMPP MUC domain. FIXME: use XEP-0030 to discover it.

muc: \'conference.raj-openfire.magnet.com\'

bosh: \'// raj-openfire.magnet.com/http-bind\',

cd /etc/nginx/site-enabled/. Open jitsi meet file

upstream xmpp-failover {

server raj-openfire.magnet.com:7070;

}

server {

listen 80;

server_name jitsiraj.magnet.com;

return 301 [https://\$host\$request_uri;]{.underline}

}

server {

listen 443 ssl;

server_name jitsiraj.magnet.com;

ssl_certificate /etc/nginx/star_magnet_com.crt;

ssl_certificate_key /etc/nginx/star_magnet_com.key;

root /srv/jitsi-meet;

index index.html index.htm;

location \~ \^/(\[a-zA-Z0-9\_\]+)\$ {

rewrite \^/(.\*)\$ / break;

}

location / {

ssi on;

}

\# BOSH

location /http-bind {

proxy_pass [http://xmpp-failover/http-bind;]{.underline}

proxy_set_header X-Forwarded-For \\\$remote_addr;

proxy_set_header Host \\\$http_host;

}

\# xmpp websockets

location /xmpp-websocket {

proxy_pass [http://xmpp-failover;]{.underline}

proxy_http_version 1.1;

proxy_set_header Upgrade \\\$http_upgrade;

proxy_set_header Connection \\\"upgrade\\\";

proxy_set_header Host \\\$host;

tcp_nodelay on;

}

}
