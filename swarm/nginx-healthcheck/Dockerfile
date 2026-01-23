FROM nginx:alpine

# Копируем HTML файл
COPY index.html /usr/share/nginx/html/index.html

# Устанавливаем curl для healthcheck
RUN apk add --no-cache curl

# Настраиваем healthcheck
HEALTHCHECK --interval=30s --timeout=3s --start-period=5s --retries=3 \
  CMD curl -f http://localhost/ | grep -q "Hello" || exit 1

EXPOSE 80