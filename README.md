# HCHC Manager

A full-stack web application for organization/community management focused on professional networking events (conferences, meetups, workshops).

## Features

- **Quick Onboarding**: 5-step onboarding process (~4 minutes)
- **Closed-Door Events**: All events require application and admin approval
- **Attendance Tracking**: Admins can track event attendance
- **Contact Management**: Manager/admin access to organization contact database
- **Network Visualization**: Visual network graphs for managers
- **LLM Enrichment**: AI-powered profile enrichment and application review assistance

## Tech Stack

- **Frontend**: Next.js 14+ with TypeScript, Tailwind CSS, shadcn/ui
- **Backend**: Node.js with Express, TypeScript, Prisma ORM
- **Database**: PostgreSQL
- **Authentication**: JWT with email verification
- **LLM**: OpenAI API / Anthropic Claude

## Getting Started

### Prerequisites

- Node.js >= 18.0.0
- npm >= 9.0.0
- PostgreSQL database

### Installation

```bash
# Install all dependencies
npm run install:all

# Set up environment variables
cp server/.env.example server/.env
cp client/.env.example client/.env

# Run database migrations
cd server
npx prisma migrate dev

# Start development servers
npm run dev
```

## Project Structure

```
hchc_manager/
├── server/          # Backend API (Express + TypeScript + Prisma)
├── client/          # Frontend (Next.js + TypeScript)
└── BRAINSTORM.md    # Planning document
```

## Development

- `npm run dev` - Start both server and client in development mode
- `npm run build` - Build both server and client for production

## License

Private - All rights reserved

