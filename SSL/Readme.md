# HTTP server block
server {
    listen 80;  # HTTP
    server_name yourdomain.com;

    # Redirect all HTTP requests to HTTPS
    return 301 https://$host$request_uri;
}

# HTTPS server block
server {
    listen 443 ssl;  # HTTPS
    server_name yourdomain.com;

    ssl_certificate /ssl/fullchain1.pem;   # Path to your certificate
    ssl_certificate_key /ssl/privkey1.pem;  # Path to your private key

    location / {
        proxy_pass http://localhost:7575;  # Change to localhost
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
    }
}
