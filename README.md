# GrayLog
Graylog Docker deployment with Persistent Storage and TLS 

After gitclone this repo 

# Create and set permissions
sudo mkdir -p /opt/graylog/{graylog_journal,opensearch,mongo,nginx/certs}

sudo chown -R 1100:1100 /opt/graylog/graylog_journal

sudo chown -R 1000:1000 /opt/graylog/opensearch

sudo chown -R 999:999   /opt/graylog/mongo

# Start it all up 
docker compose up -d


