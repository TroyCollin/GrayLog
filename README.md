# GrayLog
Graylog Docker deployment with Persistent Storage and TLS 

After gitclone this repo 

# Create and set permissions
sudo mkdir -p /opt/graylog/{graylog_journal,opensearch,mongo,nginx/certs}

sudo chown -R 1100:1100 /opt/graylog/graylog_journal

sudo chown -R 1000:1000 /opt/graylog/opensearch

sudo chown -R 999:999   /opt/graylog/mongo

# Create self signed certs or place your own in /opt/nginx/certs/

openssl req -x509 -nodes -days 365 \
            -newkey rsa:2048 \
            -keyout /certs/graylog.key \
            -out /certs/graylog.crt \
            -subj '/CN=logs.nattech.net';


# Start it all up 
docker compose up -d


