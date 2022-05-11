# nginx-forward-localport-example
> Tested on Ubuntu 20.04, app is running on port 5000
### **How To**
1. Update Ubuntu
```
sudo apt update
```
2. Install nginx
```
sudo apt install nginx
```
3. Update default site-available nginx
```
sudo vim /etc/nginx/sites-available/default
```
> Update with value below
```
server {
        listen 80 default_server;
        listen [::]:80 default_server;
        server_name update_with_ip_public;
        location / {
                proxy_pass http://127.0.0.1:5000;
        }
}
```
4. Reload nginx configuration
```
sudo systemctl reload nginx
```
5. Check nginx status
```
systemctl status nginx
```
