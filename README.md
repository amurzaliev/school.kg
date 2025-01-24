# Install

- Configure NGINX
```
sudo nano /etc/nginx/sites-available/school.kg
```
```
server {
    listen 80;
    server_name www.school.kg school.kg;
    root /var/www/school.kg/maintain-page;
    location / {
      try_files $uri $uri/ /index.html;
    }
}
```
```
sudo ln -s /etc/nginx/sites-available/school.kg /etc/nginx/sites-enabled/
```

- Install Let's encrypt

```
sudo certbot --nginx -d www.school.kg -d school.kg
sudo nginx -t
sudo systemctl restart nginx
```

- Install project
```
cd /var/www
sudo mkdir school.kg
sudo chown -R adilet:adilet school.kg
git clone git@github.com:amurzaliev/school.kg.git school.kg
```
