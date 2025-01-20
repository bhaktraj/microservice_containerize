FROM node:14 AS First_image
WORKDIR /app
COPY ./ ./nodeapi/
RUN cd nodeapi && npm install
FROM node:14 
WORKDIR /app
COPY --from=First_image /app/nodeapi/ /app/
CMD [ "/bin/sh", "-c", "cd /app/ && npm start" ]