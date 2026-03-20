FROM node:20-alpine

ARG REACT_APP_API_URL=
ARG REACT_APP_VALID_EMAIL=patient@healthcare.com
ARG REACT_APP_VALID_PASSWORD=password123

WORKDIR /app

COPY package.json package-lock.json* ./
RUN npm install --legacy-peer-deps

COPY . .
ENV CI=false
ENV GENERATE_SOURCEMAP=false
ENV REACT_APP_API_URL=$REACT_APP_API_URL
ENV REACT_APP_VALID_EMAIL=$REACT_APP_VALID_EMAIL
ENV REACT_APP_VALID_PASSWORD=$REACT_APP_VALID_PASSWORD

RUN npm run build

COPY server.js ./

EXPOSE 3005

CMD ["node", "server.js"]
