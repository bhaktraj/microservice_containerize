FROM node:14 AS first_image
WORKDIR /app
COPY ./ /app/client/
RUN cd client && npm install && npm run build --prod

#second image
FROM nginx:latest
COPY --from=first_image /app/client/dist/client /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.config
EXPOSE 4200
