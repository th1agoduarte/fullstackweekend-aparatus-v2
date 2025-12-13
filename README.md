This is a [Next.js](https://nextjs.org) project bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

## Getting Started

### 1. Install Dependencies

```bash
npm install
```

### 2. Setup Database

Start the PostgreSQL database with Docker:

```bash
docker compose up -d
```

### 3. Configure Environment Variables

Create a `.env` file in the root directory:

```env
DATABASE_URL="postgresql://postgres:postgres@localhost:5432/aparatus"
```

### 4. Run Prisma Migrations

Apply database migrations:

```bash
npx prisma migrate dev
```

This command will:
- Create the database schema
- Generate the Prisma Client
- Apply all pending migrations

### 5. Seed the Database

Populate the database with initial data:

```bash
npx prisma db seed
```

### 6. Run the Development Server

Start the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/app/building-your-application/optimizing/fonts) to automatically optimize and load [Geist](https://vercel.com/font), a new font family for Vercel.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/new?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/app/building-your-application/deploying) for more details.

## Database Commands

### View Database in Prisma Studio

```bash
npx prisma studio
```

This opens a visual editor for your database at [http://localhost:5555](http://localhost:5555)

### Create a New Migration

After changing the Prisma schema:

```bash
npx prisma migrate dev --name your_migration_name
```

### Reset Database

To reset the database and reapply all migrations:

```bash
npx prisma migrate reset
```

This will:
- Drop the database
- Recreate the database
- Apply all migrations
- Run the seed script

### Generate Prisma Client

If you need to regenerate the Prisma Client:

```bash
npx prisma generate
```

## Docker Commands

### Start Database

```bash
docker compose up -d
```

### Stop Database

```bash
docker compose down
```

### View Database Logs

```bash
docker compose logs postgres -f
```

### Remove Database Volume (Clear all data)

```bash
docker compose down -v
```
