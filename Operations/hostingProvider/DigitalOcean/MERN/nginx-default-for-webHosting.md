Frontend and Backend setup:


dermatologybooks.org

www.dermatologybooks.org

server.dermatologybooks.org

http://server.dermatologybooks.org/

sudo certbot --nginx -d server.dermatologybooks.org

dermatologybooks_frontend

dermatologybooks_server



  		   proxy_pass http://localhost:9000;
                 proxy_http_version 1.1;
                 proxy_set_header Upgrade $http_upgrade;
                 proxy_set_header Connection 'upgrade';
                 proxy_set_header Host $host;
                 proxy_cache_bypass $http_upgrade;
				 
				 
				 
				 
				 
				 
server {
       listen 80;
       listen [::]:80;

       server_name server.dermatologybooks.org;

       root /var/www/dermatologybooks_server;
       index index.html;

       location / {
		   proxy_pass http://localhost:5000;
                 proxy_http_version 1.1;
                 proxy_set_header Upgrade $http_upgrade;
                 proxy_set_header Connection 'upgrade';
                 proxy_set_header Host $host;
                 proxy_cache_bypass $http_upgrade;
       }

}