# Install

1. Configure NGINX
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

2. Install Let's encrypt

```
sudo certbot --nginx -d www.school.kg -d school.kg
sudo nginx -t
sudo systemctl restart nginx
```
