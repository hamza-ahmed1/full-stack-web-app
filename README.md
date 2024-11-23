# Web App Developed by Hamza A.K

This web app is developed by **Hamza A.K**, designed and built from scratch with the latest technologies like **Prisma** for database management and **PostgreSQL** as the relational database.

## How to Set Up the Project

### Step 1: Set Up Prisma
1. Go to the [Prisma documentation](https://www.prisma.io/docs) and choose the **Start from Scratch** guide to set up your Prisma environment.
2. Copy the Prisma schema from your newly created project and paste it into the `schema.prisma` file of your project.

### Step 2: Set Up PostgreSQL with Docker
1. Run a Docker image for PostgreSQL and set the following environment variables:
   - `POSTGRES_USER`: `hamza`
   - `POSTGRES_PASSWORD`: `hamza1234`
   - `POSTGRES_DB`: `school`

### Step 3: Run Migrations
1. After setting up Prisma and the database, run the following migration command to apply your Prisma schema to the database:

   npx prisma migrate dev
### Step 4: Launch Prisma Studio
To view and manage your database directly, launch Prisma Studio:
npx prisma studio
This will open Prisma Studio on localhost:5555, where you can view and manage your database records.
### Step 5: Add Seed Data
Create a seed.ts file to populate the database with some initial data. Here’s an example of a seed file:

import { PrismaClient } from "@prisma/client";

const prisma = new PrismaClient();

async function main() {
  await prisma.user.create({
    data: {
      name: 'Hamza A.K',
      email: 'hamza@example.com',
    },
  });
}

main()
  .catch(e => {
    throw e;
  })
  .finally(async () => {
    await prisma.$disconnect();
  });
This will add a user with the name Hamza A.K and email hamza@example.com.
### Step 6: Set Up Prisma Client
In the lib directory, create a prisma.ts file with the following content:

import { PrismaClient } from "@prisma/client";

export const prisma = new PrismaClient();
### Step 7: Modify package.json for Prisma Seed
Add the following configuration in the package.json file under the "prisma" section to enable seeding of the database with the Prisma CLI:

"prisma": {
  "seed": "ts-node --compiler-options {\"module\":\"CommonJS\"} prisma/seed.ts"
}
### Step 8: Install Dependencies
Install the necessary development dependencies, including ts-node for running TypeScript files:

npm install --save-dev ts-node
### Step 9: Seed the Database
Finally, seed the database by running the following command:

npx prisma db seed
### About Hamza A.K
This web application is developed by Hamza A.K, a passionate developer with a focus on full-stack development and modern web technologies. The project incorporates Prisma ORM for efficient database management, ensuring smooth database interaction and scalability.

Technologies Used
Prisma ORM
PostgreSQL
Docker (for local database setup)
TypeScript
Next.js (for web framework)
Feel free to explore and contribute to the repository!

## Developed by Hamza A.K. All rights reserved.



### Explanation of Changes:
1. **Step-by-Step Instructions**: Each step is clearly numbered with a short description followed by the code snippets required for that step.
2. **Prisma Studio** launch step (Step 4) is now clearly explained with the command `npx prisma studio` and a note that the database can be managed at [localhost:5555](http://localhost:5555).
3. **Seed Data**: A sample `seed.ts` file is included under **Step 5**.
4. **Prisma Client Setup**: Step 6 describes how to set up Prisma Client with the required `prisma.ts` file.
5. **Final Steps**: The remaining steps guide you on modifying `package.json`, installing dependencies, and seeding the database.

