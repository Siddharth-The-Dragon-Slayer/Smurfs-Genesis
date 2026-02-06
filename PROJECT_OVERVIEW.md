# Quantum Stash - Inventory Management SaaS

## Overview

Quantum Stash is a modern, full-stack inventory management SaaS application built with Next.js 14, designed for e-commerce businesses and companies requiring comprehensive stock control. The application provides a complete solution for managing inventory, warehouses, categories, brands, and items with an intuitive user interface.

## What This Application Does

### Core Features

**1. Inventory Management**
- Track items with detailed information (name, SKU, barcode, quantity)
- Manage product dimensions (width, height, depth, weight)
- Set pricing (selling price, purchase price, tax rates)
- Monitor stock levels with reorder points
- Upload and manage product images
- Track suppliers and warehouse locations

**2. Organization & Categorization**
- Create and manage warehouses with types and locations
- Organize products by categories
- Group items by brands
- Define measurement units (pieces, kg, meters, etc.)

**3. User Authentication & Authorization**
- Email/password authentication (with auto-verification)
- OAuth integration (Google & GitHub) - requires setup
- Role-based access control (user/admin)
- Password reset functionality
- Secure session management with JWT and HTTP-only cookies

**4. Data Management**
- PostgreSQL database with Neon serverless hosting
- Type-safe database operations with Drizzle ORM
- Prepared statements for optimized queries
- Complex relational data models

## Technology Stack

### Frontend
- **Framework**: Next.js 14 (App Router)
- **UI Library**: React 18
- **Styling**: Tailwind CSS
- **UI Components**: shadcn/ui (Radix UI primitives)
- **Forms**: React Hook Form with Zod validation
- **State Management**: React hooks and server actions
- **Image Handling**: react-cropper, react-dropzone
- **Tables**: TanStack Table

### Backend
- **Runtime**: Node.js 20+
- **Database**: PostgreSQL (Neon serverless)
- **ORM**: Drizzle ORM
- **Authentication**: NextAuth v5 (beta)
- **API**: Next.js Server Actions
- **Validation**: Zod schemas

### Infrastructure
- **Hosting**: Vercel (recommended)
- **Database**: Neon (serverless Postgres)
- **Email**: Resend (optional, for transactional emails)
- **File Upload**: UploadThing (optional)
- **SSL**: HTTPS support with local certificates

## Database Schema

### Core Tables

**Users**
- Authentication and profile information
- Role-based permissions (user/admin)
- Email verification status
- Password reset tokens

**Items (Inventory)**
- Product details (name, description, barcode, SKU)
- Pricing information (selling, purchase, tax)
- Physical dimensions and weight
- Stock quantity and reorder points
- Warehouse assignment
- Category and brand associations
- Supplier information
- Product images (JSON array)
- Timestamps (created, updated)

**Warehouses**
- Name and type
- Location information
- Description

**Categories**
- Product categorization
- Hierarchical organization support

**Brands**
- Brand management
- Product associations

**Units**
- Measurement units (kg, pieces, meters, etc.)
- Abbreviations

**Authentication Tables**
- Accounts (OAuth providers)
- Sessions (active user sessions)
- Verification tokens

## Project Structure

```
src/
├── actions/          # Server actions (auth, CRUD operations)
├── app/             # Next.js app router pages
├── components/      # React components
│   ├── forms/       # Form components
│   ├── ui/          # shadcn/ui components
│   └── emails/      # Email templates
├── config/          # App configuration
├── db/              # Database setup
│   ├── schema/      # Drizzle schemas
│   ├── migrations/  # Database migrations
│   └── prepared/    # Prepared statements
├── hooks/           # Custom React hooks
├── lib/             # Utility functions
├── providers/       # Context providers
├── styles/          # Global styles
├── types/           # TypeScript types
└── validations/     # Zod schemas
```

## Key Modifications Made

1. **Email Verification Removed**: Users are auto-verified upon signup for easier onboarding
2. **Placeholder Credentials**: OAuth and email services use placeholders for development
3. **Environment Variables**: Configured for local development with Neon database

## Getting Started

### Prerequisites
- Node.js 20.10.0 or higher
- npm or pnpm
- Neon PostgreSQL database account

### Installation

1. **Install dependencies**:
```bash
npm install --legacy-peer-deps
```

2. **Set up environment variables** (`.env`):
```env
# Database
DATABASE_URI="your-neon-postgres-connection-string"

# Authentication
NEXTAUTH_URL="https://localhost:3000"
AUTH_SECRET="your-generated-secret"

# Optional OAuth (use placeholders for development)
GOOGLE_ID="placeholder"
GOOGLE_SECRET="placeholder"
GITHUB_ID="placeholder"
GITHUB_SECRET="placeholder"

# Optional Services
UPLOADTHING_SECRET="placeholder"
UPLOADTHING_APP_ID="placeholder"
RESEND_API_KEY="placeholder"
```

3. **Push database schema**:
```bash
npm run db:push
```

4. **Start development server**:
```bash
npm run dev
```

The app will be available at `https://localhost:3000`

## Available Scripts

- `npm run dev` - Start development server with HTTPS
- `npm run build` - Build for production
- `npm run start` - Start production server
- `npm run db:push` - Push schema changes to database
- `npm run db:studio` - Open Drizzle Studio (database GUI)
- `npm run db:generate` - Generate migrations
- `npm run lint` - Run ESLint
- `npm run typecheck` - Run TypeScript type checking

## Features in Development

- Stripe payment integration
- Advanced reporting and analytics
- Multi-organization support
- Email notifications
- Export/import functionality
- Mobile responsive improvements
- Real-time inventory updates

## Security Features

- Bcrypt password hashing
- HTTP-only cookies for sessions
- CSRF protection
- SQL injection prevention (prepared statements)
- XSS protection
- Environment variable validation
- Role-based access control

## Performance Optimizations

- Server-side rendering (SSR)
- Static generation where applicable
- Image optimization
- Database connection pooling
- Prepared SQL statements
- Code splitting
- Lazy loading

## Contributing

This is a portfolio/demo project. Feel free to fork and customize for your needs.

## License

MIT License - See LICENSE file for details

## Author

Original Author: Piotr Borowiecki
- Website: https://pjborowiecki.com
- GitHub: https://github.com/pjborowiecki

## Support

For issues or questions, please open an issue on the GitHub repository.
