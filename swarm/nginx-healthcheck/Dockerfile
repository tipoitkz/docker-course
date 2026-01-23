FROM nginx:alpine

# Кладём страницу и конфиг
COPY html /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf

# Healthcheck: страница должна реально содержать "Hello"
HEALTHCHECK --interval=10s --timeout=3s --retries=3 \
CMD wget -qO- http://localhost/ | grep -q "Hello" || exit 1