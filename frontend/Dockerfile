# FROM ghcr.io/cirruslabs/flutter:stable AS build
# WORKDIR /app

# COPY pubspec.yaml .
# COPY pubspec.lock .
# RUN flutter pub get

# COPY . .
# RUN flutter config --enable-web
# RUN flutter build web

# FROM nginx:alpine
# COPY nginx.conf /etc/nginx/conf.d/default.conf
# COPY --from=build /app/build/web /usr/share/nginx/html

# EXPOSE 80

FROM nginxinc/nginx-unprivileged:stable-alpine

COPY build/web /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 8080