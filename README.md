# Expense Tracker (Next.js, TypeScript, Neon & Clerk)

A modern, full-stack expense tracking application built with Next.js and TypeScript. It allows users to log and manage income and expenses securely. The app leverages:

- **Next.js** for server-side rendering and routing
- **Neon** for PostgreSQL database hosting
- **Prisma** as the the ORM for database interactions
- **Clerk** for user authentication and management

## Features

- User authentication with Clerk
- Add, edit, and delete income and expense entries
- Categorize transactions
- View transaction history
- Responsive design for mobile and desktop

## Technologies Used

- Next.js
- TypeScript
- Neon (PostgreSQL, database)
- Prisma
- Clerk (Authentication)
- Tailwind CSS

## Usage

### Prerequisites

- Node.js
- Package manager
- Neon account for database
- Clerk account for authentication

## Installation

1. Clone the repository:

```bash
git clone https://github.com/ericstober/expense-tracker-nextjs.git
cd expense-tracker-nextjs
```

2. Install dependencies:

```bash
npm install
```

3. Add Environment Variables:

Rename the `.env.example` file to `.env.local` and add the following values:

- `DATABASE_URL`: Your db string from https://neon.tech
- `NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY`: Your Clerk public frontend API key from https://dashboard.clerk.dev/settings/api-keys
- `CLERK_SECRET_KEY`: Your Clerk secret key from https://dashboard.clerk.dev/settings/api-keys

4. Rub database migration:

```bash
npx prisma migrate dev --name init
```

5. Run the development server:

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

## Project Structure

```
expense-tracker-nextjs/
├── app/                # Next.js app directory
├── components/         # Reusable UI components
├── lib/                # Utility functions and libraries
├── prisma/             # Prisma schema and migrations
├── public/             # Static assets
├── types/              # TypeScript type definitions
├── .env.example        # Example environment variables
├── middleware.ts       # Middleware for authentication
├── next.config.mjs     # Next.js configuration
├── package.json        # Project metadata and scripts
└── tsconfig.json       # TypeScript configuration
```

## Scripts

- `npm run dev`: Start the development server
- `npm run build`: Build the application for production
- `npm run start`: Start the production server
- `npx prisma studio`: Launch Prisma Studio for database management

## Authentication with Clerk

This application uses Clerk for user authentication. To set up Clerk:

1. Sign up at [Clerk](https://clerk.com/)
2. Create a new application
3. Obtain the **Publishable Key** and **Secret Key** from the Clerk dashboard
4. Add these keys to your `.env.local` file as shown above

## Database with Neon and Prisma

The application uses Neon for hosting the PostgreSQL database and Prisma as the ORM.

1. Sign up at [Neon](https://neon.tech/)
2. Create a new project and obtain the database connection string
3. add the connection string to your `.env.local` file as `DATABASE_URL`
4. Run Prisma migrations to set up the database schema:

```bash
npx prisma migrate dev --name init
```
