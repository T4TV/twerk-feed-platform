# Twerk Feed Platform

A modern web-based video feed platform for discovering and sharing short-form video content. Built with Next.js, TypeScript, PostgreSQL, and Cloudflare R2.

## Tech Stack

- **Frontend**: Next.js 14 + React 18 + TypeScript
- **Styling**: Tailwind CSS + Shadcn UI
- **Backend**: Next.js API Routes + Node.js
- **Database**: PostgreSQL + Prisma ORM
- **Caching**: Redis
- **Storage**: Cloudflare R2 / AWS S3
- **Authentication**: JWT + bcryptjs

## Features

- ✅ Infinite scroll video feed
- ✅ User authentication (register/login)
- ✅ Video upload with virus scanning
- ✅ Like and comment system
- ✅ User profiles
- ✅ Follow/unfollow users
- ✅ Cursor-based pagination
- ✅ Rate limiting
- ✅ Mobile-first responsive design

## Getting Started

### Prerequisites

- Node.js 18+
- PostgreSQL 14+
- Redis 6+
- AWS/Cloudflare R2 credentials

### Installation

1. Clone the repository
```bash
git clone https://github.com/T4TV/twerk-feed-platform.git
cd twerk-feed-platform
```

2. Install dependencies
```bash
npm install
```

3. Set up environment variables
```bash
cp .env.example .env.local
# Edit .env.local with your credentials
```

4. Set up the database
```bash
npm run prisma:migrate
```

5. Start the development server
```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - Login user

### Videos
- `GET /api/videos/feed` - Get paginated video feed
- `POST /api/videos/upload` - Upload a new video
- `POST /api/videos/:id/like` - Like/unlike a video
- `POST /api/videos/:id/comment` - Add a comment to a video

### Users
- `GET /api/users/:id` - Get user profile
- `POST /api/users/:id/follow` - Follow a user

## Project Structure

```
├── src/
│   ├── app/
│   │   ├── api/              # API routes
│   │   ├── (auth)/           # Auth pages
│   │   ├── globals.css       # Global styles
│   │   └── page.tsx          # Home page
│   ├── components/           # Reusable React components
│   ├── hooks/                # Custom React hooks
│   └── lib/                  # Utility functions
├── prisma/
│   └── schema.prisma         # Database schema
├── .github/workflows/        # CI/CD workflows
└── next.config.js            # Next.js configuration
```

## Development

### Database Migrations
```bash
# Create a new migration
npm run prisma:migrate

# Open Prisma Studio
npm run prisma:studio
```

### Testing
```bash
# Run tests
npm test

# Run tests in watch mode
npm run test:watch
```

### Linting
```bash
npm run lint
```

## Deployment

### Vercel (Recommended)

1. Push your code to GitHub
2. Connect your repository to Vercel
3. Set environment variables in Vercel dashboard
4. Deploy automatically on push to main branch

### Custom Server

1. Build the project
```bash
npm run build
```

2. Start production server
```bash
npm start
```

## Security Considerations

- ⚠️ Always use HTTPS in production
- ⚠️ Keep JWT_SECRET secure and rotate regularly
- ⚠️ Implement CORS appropriately
- ⚠️ Validate and sanitize all user inputs
- ⚠️ Implement content moderation (e.g., AWS Rekognition)
- ⚠️ Set up rate limiting on all public endpoints

## License

MIT

## Support

For issues and feature requests, please create a GitHub issue.
