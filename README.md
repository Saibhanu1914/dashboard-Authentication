# Pizza Dashboard - Next.js with Google Authentication

A modern, responsive dashboard application built with Next.js, featuring Google OAuth authentication and pizza order management.

## Features

- **Google OAuth Authentication** using NextAuth.js
- **Protected Routes** with middleware-based authentication
- **Responsive Design** that works on desktop, tablet, and mobile
- **Pizza Orders Management** with sorting and filtering capabilities
- **Modern UI** built with Tailwind CSS and shadcn/ui components
- **TypeScript** for type safety
- **Server-Side Rendering** with Next.js App Router

## Technology Stack

- **Framework**: Next.js 14+ (App Router)
- **Authentication**: NextAuth.js with Google Provider
- **Styling**: Tailwind CSS
- **UI Components**: shadcn/ui
- **Language**: TypeScript
- **Deployment**: Vercel

## Prerequisites

Before running this project, make sure you have:

- Node.js 18+ installed
- A Google Cloud Console account for OAuth setup
- Git for version control

## Installation & Setup

### 1. Clone the Repository

\`\`\`bash
git clone <your-repository-url>
cd pizza-dashboard
\`\`\`

### 2. Install Dependencies

\`\`\`bash
npm install
\`\`\`

### 3. Environment Variables Setup

Create a `.env.local` file in the root directory:

\`\`\`env
GOOGLE_CLIENT_ID=your_google_client_id_here
GOOGLE_CLIENT_SECRET=your_google_client_secret_here
NEXTAUTH_SECRET=your_nextauth_secret_here
NEXTAUTH_URL=http://localhost:3000
\`\`\`

### 4. Google OAuth Setup

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project or select existing one
3. Enable the Google+ API
4. Go to "Credentials" → "Create Credentials" → "OAuth client ID"
5. Choose "Web application"
6. Add authorized redirect URIs:
   - Development: `http://localhost:3000/api/auth/callback/google`
   - Production: `https://yourdomain.com/api/auth/callback/google`
7. Copy the Client ID and Client Secret to your `.env.local`

### 5. Generate NextAuth Secret

\`\`\`bash
openssl rand -base64 32
\`\`\`

Add the generated string as `NEXTAUTH_SECRET` in your `.env.local`

### 6. Run the Development Server

\`\`\`bash
npm run dev
\`\`\`

Open [http://localhost:3000](http://localhost:3000) in your browser.

## Application Structure

\`\`\`
├── app/
│   ├── api/auth/[...nextauth]/     # NextAuth API routes
│   ├── dashboard/                  # Protected dashboard pages
│   │   ├── orders/                 # Pizza orders page
│   │   └── layout.tsx              # Dashboard layout
│   ├── globals.css                 # Global styles
│   ├── layout.tsx                  # Root layout
│   └── page.tsx                    # Home/login page
├── components/                     # Reusable components
│   ├── ui/                         # shadcn/ui components
│   ├── auth-provider.tsx           # Authentication provider
│   ├── dashboard-nav.tsx           # Dashboard navigation
│   ├── login-button.tsx            # Google login button
│   └── user-account-nav.tsx        # User account dropdown
├── lib/                            # Utility functions and data
│   ├── data.ts                     # Mock pizza orders data
│   ├── types.ts                    # TypeScript type definitions
│   └── utils.ts                    # Utility functions
└── middleware.ts                   # Route protection middleware
\`\`\`

## Key Features

### Authentication
- Google OAuth integration
- Automatic redirect for authenticated users
- Protected routes with middleware
- Secure session management

### Dashboard Pages
1. **Welcome Page** (`/dashboard`)
   - Personalized greeting with user's name
   - Clean, modern interface

2. **Pizza Orders Page** (`/dashboard/orders`)
   - Sortable table columns (Order ID, Customer, Date, etc.)
   - Status filtering (All, Pending, Preparing, etc.)
   - Search functionality across orders
   - Color-coded status badges
   - Responsive table design

### UI/UX Features
- Fully responsive design
- Loading states during authentication
- Error handling for failed operations
- Intuitive navigation
- Clean, modern interface
- Dark/light theme support

## Deployment

### Vercel Deployment

1. Push your code to GitHub
2. Connect your repository to Vercel
3. Add environment variables in Vercel dashboard:
   - `GOOGLE_CLIENT_ID`
   - `GOOGLE_CLIENT_SECRET`
   - `NEXTAUTH_SECRET`
   - `NEXTAUTH_URL` (your production URL)
4. Deploy!

## Challenges Faced

- Ensuring proper authentication flow with NextAuth.js
- Creating a responsive table that works well on mobile devices
- Implementing sorting and filtering functionality
- Managing protected routes with middleware

## Third-Party Libraries

- **next-auth**: Authentication
- **lucide-react**: Icons
- **clsx** and **tailwind-merge**: Utility for conditional class names
- **shadcn/ui**: UI components

## Author

Your Name

## License

This project is licensed under the MIT License.
\`\`\`

Let's create a package.json file:
