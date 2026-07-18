# creating a base image
FROM mhart/alpine-node AS base
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install

# Create the development image (used when building
# the image with --target development)
FROM base AS development            
COPY . .
CMD ["npm", "run", "dev"]

# Create the production image (used when building
# the image with --target production)
FROM base AS production
COPY . .
# Remove dev dependencies
RUN npm prune --production
CMD ["npm", "run", "start"]


# You MUST specify the target stage (e.g., `dev` or `prod`) when building the image.
# If you don't, Docker builds the image from the last stage in the Dockerfile.
# Since the final stage in this Dockerfile is `prod`, omitting `--target` produces a production image.