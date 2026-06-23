FROM nginx:alpine

COPY index.html /usr/share/nginx/html/index.html

RUN rm -f /etc/nginx/conf.d/default.conf

RUN printf 'server {\n\
    listen 8080;\n\
    listen [::]:8080;\n\
    server_name _;\n\
    location / {\n\
        root /usr/share/nginx/html;\n\
        index index.html;\n\
    }\n\
}\n' > /etc/nginx/conf.d/default.conf

EXPOSE 8080

CMD ["nginx", "-g", "daemon off;"]
