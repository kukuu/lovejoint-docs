# Lovejoint Documentation

Love Joint is a  focused  Product Engineering enterprise business. It specialises in Nutraceutical  Lifestyle & Healthy Living Boosters®.

In this project, we will be using Apollo Server and Apollo client libraries to handle data fetching. We will also dockerize it. 

### Repository (* Private)

https://github.com/kukuu/lovejoint

### Production

https://www.lovejoint.store/

### Technologies

1. Next.js
2. React 
3. ApolloGraphQL 
4. TailwindCSS
5. Casual ( for fake data)
6. Docker
7. Heroku (for deployment) 
8. Jest for unit testing
9. Cypress (e2e)
10. Supabase (Postgres Database service) - middleware to connect Prisma Studio to Postgres in AWS. 
11. Nexus ( Adding typedefs to Graph QL)
12. Prisma (Middleware -  ORM to work with Postgres Database like - modelling, migration,generate SQL query)
13. Prisma Client- It simplifies database access and management in web and application development, providing a higher-level, type-safe interface for working with
relational databases. It's particularly popular in the Node.js ecosystem and is widely used for building modern web applications and APIs.
14. STRIPE ( payment integration)
15. PayPal( payment integration)
16. Apache KAFKA

### Run commands to get started

- npm install (install all the dependencies)
- npm run dev (for fast refresh)
- npm run build (production build)
- npm run start ( after production build)
- npm run test ( unit testing)

### Build Docker Container

- docker build -t nextjs-docker .

### Run Docker

- docker run -p 3000:3000 nextjs-docker

(Default port)

### Pushing Docker Image to Docker Hub

- Docker Login
- docker tag nextjs-docker alexmorgan/nextjs-docker:version1.0
- docker push alexmorgan/nextjs-docker
- Go to Docker hub and then refresh
- Pull the uploaded image by using command: docker pull username/imageName:versionName
- Run it in your internal system command line.
- Then finally there should be no change with your internal image.

### Push Docker Link Image

- docker push techlever45/awesome-links-web:version1

### Docker Image link

- https://hub.docker.com/repository/docker/techlever45/awesome-links-web
- command: docker pull techlever45/awesome-links-web:version1

### e2e testing using Cypress

- npm run e2e [ this will run the test in headless mode]
- npm run cypress [ this will run the test after opening Browser]

### Deploy to Heroku

- heroku login
- heroku create
- heroku stack:set container
- git push heroku master

### Spin up your Database

- [Supabase DB setup](docs/databaseSetup.md)

### Configuration Requirements

- next.config.js
  - ensure you have listed all the domains you will be using for images in next.config.js. Like drive.google.com or cloudinary.com etc.
- .env
  - Replace DATABASE_URL with actual database url from Supabase dashboard. (* held in private repository).
  - NEXTAUTH_URL has to be replaced with your domain.
  - SECRET can be generate using secret generator site like -
  - Ensure you have duly populated all the id and secret field for different auth provider like Google, Facebook, Twitter etc.
  - [ Auth Setup](docs/authProviders.md)
- .env.local
  - NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY has to be obtained from Stripe dashboard.
  - STRIPE_SECRET_KEY has to be obtained from stripe dashboard.
  - STRIPE_WEBHOOK_SECRET has to be generated using CLI or using Stripe dashboard.
  - [Stripe Setup](docs/stripeSetup.md)

### [References/docs](docs/allReferences.md) - (* held in private repository).

### Adding Mutiple Product Images
1. Prisma schema update
2. ExtraImage.ts file added to graphql/types
3. Updated graphql/types/index.ts
4. Updated pages/product/[pid].ts
5. Updated components/ProductDetail.tsx
6. Autoupdated graphql/schema.graphql

After schema change 

```
npx prisma migrate dev

```
will have to be executed.
