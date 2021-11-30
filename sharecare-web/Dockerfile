FROM node:12-alpine

ENV PORT=80 

# Metadata as defined in OCI image spec annotations - https://github.com/opencontainers/image-spec/blob/master/annotations.md
LABEL org.opencontainers.image.title="CHANGE_MY_VALUE" \
      org.opencontainers.image.description="CHANGE_MY_VALUE" \
      org.opencontainers.image.authors="CHANGE_MY_VALUE" \
      org.opencontainers.image.vendor="CHANGE_MY_VALUE"

# add debugging utilities
RUN apk --no-cache add \
  curl \
  ca-certificates \
  jq \
  less \
  vim

# bundle app and install dependencies 
COPY . /app
WORKDIR /app
RUN npm install

# run application
EXPOSE $PORT
CMD npm start