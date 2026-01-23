version: '3.8'

services:
  web:
    image: nginx:alpine
    container_name: nginx-healthcheck
    ports:
      - "8080:80"
    volumes:
      - ./html:/usr/share/nginx/html:ro
    healthcheck:
      test: ["CMD-SHELL", "wget -q -O- http://localhost/ | grep -q 'Hello'"]
      interval: 30s
      timeout: 3s
      start_period: 5s
      retries: 3
~