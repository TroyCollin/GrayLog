# GrayLog
Graylog Docker deployment with Persistent Storage and TLS 

After gitclone this repo 

edit docker-compose.yml and change to your fqdn:
 - GRAYLOG_HTTP_EXTERNAL_URI=https://logs.nattech.net/ #gray log url

   and
/CN=logs.nattech.net' # for the cert

# Create and set permissions
sudo mkdir -p /opt/graylog/{graylog_journal,opensearch,mongo,nginx/certs,nginx/conf.d}

sudo chown -R 1100:1100 /opt/graylog/graylog_journal

sudo chown -R 1000:1000 /opt/graylog/opensearch

sudo chown -R 999:999   /opt/graylog/mongo

# Create self signed certs or place your own in /opt/nginx/certs/

Certs are auto created via certgen contrainer 

# Copy Nginx config to /opt/graylog/nginx/conf.d/

sudo cp nginx/conf.d/graylog.conf /opt/graylog/nginx/conf.d/

# Start it all up 
docker compose up -d


