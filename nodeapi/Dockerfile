FROM node:14 AS FIRST_IMAGE
WORKDIR /app
COPY ./ ./nodeapi/
RUN cd nodeapi && npm install

FROM node:14
WORKDIR /app


COPY --from=FIRST_IMAGE /app/nodeapi/ /app/
EXPOSE 5000
CMD [ "/bin/sh", "-c", "cd /app/ && npm start" ]
