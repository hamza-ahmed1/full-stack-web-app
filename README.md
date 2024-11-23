# Web App Developed by Hamza A.K

This web app is developed by **Hamza A.K**, designed and built from scratch with the latest technologies like **Prisma** for database management and **PostgreSQL** as the relational database.

## How to Set Up the Project

### 1. Set Up Prisma
- Go to the [Prisma documentation](https://www.prisma.io/docs) and choose the **Start from Scratch** guide to set up your Prisma environment.
- Copy the Prisma schema from your newly created project and paste it into the `schema.prisma` file of your project.

### 2. Set Up PostgreSQL with Docker
- Run a Docker image for PostgreSQL and set the following environment variables:
  - `POSTGRES_USER`: `hamza`
  - `POSTGRES_PASSWORD`: `hamza1234`
  - `POSTGRES_DB`: `school`

### 3. Run Migrations
- After setting up Prisma and the database, run the following migration command to apply your Prisma schema to the database:
  ```bash
  npx prisma migrate dev
