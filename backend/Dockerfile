FROM node:18-alpine

WORKDIR /app

# Copy package files
COPY package*.json ./
COPY prisma ./prisma/

# Install dependencies
RUN npm ci

# Copy source code
COPY src ./src
COPY tsconfig.json ./

# Generate Prisma client
RUN npm run generate

# Expose port
EXPOSE 5000

# Start application
CMD ["npm", "run", "dev"]
