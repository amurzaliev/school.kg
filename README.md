# Install

- Configure NGINX
```
sudo nano /etc/nginx/sites-available/default
```
```
server {
    listen 80;
    server_name www.school.kg school.kg;
    root /home/adilet/projects/school.kg/maintain-page;
    location / {
      try_files $uri $uri/ /index.html;
    }
}
```

- Install Let's encrypt

```
sudo certbot --nginx -d www.school.kg -d school.kg
sudo nginx -t
sudo systemctl restart nginx
```

- Change owner of the project folder to NGINX
```
sudo chown -R www-data:www-data /home/adilet/projects/school.kg
```

- Change owner of the project folder to adilet
```
sudo chown -R adilet:adilet /home/adilet/projects/school.kg
```
