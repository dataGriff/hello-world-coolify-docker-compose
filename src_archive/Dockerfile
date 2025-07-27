FROM node:14

WORKDIR /usr/src/app

# Copy package.json and package-lock.json (if available)
COPY src/package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY src/ .

EXPOSE 3000
CMD ["node", "app.js"]