# /app /usr #lib...
FROM node:19.2-alpine3.16

# cd app
WORKDIR /app

#Dest /app
COPY package.json ./

#Instalar las dependencias
RUN npm install

#Dest /app
COPY . .

#Realizar test
RUN npm run test

#Eliminar archivos y directorios no necesarios en PROD
RUN rm -rf tests && rm -rf node_modules

#Unicamente instala las dependencias de PROD
RUN npm install --prod

#Comando RUN de la imagen
CMD [ "node", "app.js" ]
