# Placement Prep Pro & Job Application Tracking System - By Abhinav Tiwari

A comprehensive placement preparation and job application tracking system built with React, Vite, TypeScript, TailwindCSS, and Supabase.

## Features

- **Authentication**: Email/password signup and login with Supabase
- **Dashboard**: Real-time metrics and analytics for applications, interview ratios, and offer statistics
- **Applications**: Kanban-style pipeline board for managing job applications with status tracking
- **Calendar**: Interactive calendar for scheduling interviews and setting deadlines
- **Study Timer**: Pomodoro-style timer with focus session logging and tracking
- **Resume**: Upload and analyze resumes with keyword and formatting insights
- **Settings**: Integration management for LinkedIn and other services
- **Mobile Responsive**: Fully responsive design optimized for all devices

## Tech Stack

- **Frontend**: React 18, TypeScript, Vite
- **Styling**: TailwindCSS, Lucide React Icons
- **Backend**: Supabase (PostgreSQL, Auth, Storage)
- **State Management**: React Hooks with Zustand (optional)
- **Routing**: React Router DOM

## Project Structure

```
src/
├── components/          # Reusable UI components
│   ├── forms/          # Form components (AuthForm, ApplicationForm)
│   ├── dashboard/      # Dashboard components
│   ├── applications/   # Application pipeline components
│   ├── calendar/       # Calendar components
│   ├── timer/          # Timer components
│   └── resume/         # Resume components
├── hooks/              # Custom React hooks
│   ├── useSession.ts
│   ├── useApplications.ts
│   ├── useTimer.ts
│   ├── useCalendar.ts
│   └── useResume.ts
├── integrations/       # External service integrations
│   └── supabase/
│       ├── client.ts   # Supabase client setup
│       └── queries.ts  # Typed database queries
├── lib/                # Utility functions
│   ├── date.ts         # Date utilities
│   ├── analytics.ts    # Analytics calculations
│   └── alerts.ts       # Alert logic
├── pages/              # Route-level components
├── types/              # TypeScript types
│   └── db.ts          # Database entity types
├── App.tsx             # Main app with routing
├── main.tsx            # Entry point
└── index.css           # Global styles

supabase/
├── config.toml         # Supabase configuration
└── migrations/         # Database migrations
```

## Setup Instructions

### Prerequisites

- Node.js 18+
- npm or yarn
- Supabase account (free tier available)

### 1. Clone and Install Dependencies

```bash
cd Placementprep
npm install
```

### 2. Set Up Supabase

1. Create a new project at [supabase.com](https://supabase.com)
2. Get your project URL and Anon Key from Project Settings > API
3. Create a `.env.local` file:

```bash
cp .env.example .env.local
```

4. Fill in your Supabase credentials:

```env
VITE_SUPABASE_URL=your_project_url
VITE_SUPABASE_ANON_KEY=your_anon_key
```

### 3. Initialize Database

Option A: Using Supabase CLI (recommended)

```bash
npx supabase link --project-ref your_project_ref
npx supabase db push
```

Option B: Manual SQL

1. Go to Supabase Dashboard > SQL Editor
2. Copy contents from `supabase/migrations/20240101000000_initial_schema.sql`
3. Run the SQL in the editor

### 4. Start Development Server

```bash
npm run dev
```

The app will open at `http://localhost:5173`

## Building for Production

```bash
npm run build
```

Output will be in the `dist/` directory, ready for deployment.

## Environment Variables

Create a `.env.local` file with the following variables:

```env
VITE_SUPABASE_URL=https://your-project.supabase.co
VITE_SUPABASE_ANON_KEY=your-anon-key
```

## Database Schema

### Core Tables

- **profiles**: User profile information
- **applications**: Job applications with status tracking
- **study_sessions**: Study timer sessions
- **calendar_events**: Interviews, deadlines, and reminders
- **goals**: Personal placement goals
- **resumes**: Uploaded resumes with analysis
- **alerts**: Notifications and reminders
- **integrations**: Third-party service connections
- **insights**: AI-generated insights and recommendations

All tables have Row Level Security (RLS) enabled to ensure users can only access their own data.

## Available Routes

- `/login` - Authentication page
- `/dashboard` - Main dashboard with metrics
- `/applications` - Applications pipeline board
- `/applications/new` - Add new application
- `/calendar` - Calendar with events
- `/timer` - Study timer
- `/resume` - Resume upload and analysis
- `/settings` - Settings and integrations

## Features In Detail

### Dashboard
- Real-time metrics (total applications, offers, interview ratio)
- 30-day application trends
- Conversion rate tracking
- Quick statistics overview

### Applications
- Kanban-style pipeline (Applied → Shortlisted → Interview → Offered/Rejected)
- Add/edit/delete applications
- Track priority and status
- Notes and salary information
- Quick application filtering

### Calendar
- Interactive month view
- Add interviews and deadlines
- Automatic reminders
- Event details with location and company info

### Timer
- Customizable study durations
- Pause/resume functionality
- Session history
- Focus area tracking
- Auto-save completed sessions

### Resume
- PDF upload capability
- Keyword analysis
- Format scoring
- Historical tracking
- Analysis notes

## Best Practices

1. **Authentication**: Always authenticate users before accessing data
2. **Data Privacy**: RLS policies ensure users access only their data
3. **Performance**: Use React hooks efficiently, avoid unnecessary re-renders
4. **Error Handling**: Implement proper error boundaries and user feedback
5. **Mobile First**: Design components for mobile devices first

## Troubleshooting

### Supabase Connection Issues
- Verify `.env.local` has correct credentials
- Check Supabase project is active
- Ensure RLS policies are correctly set up

### Build Errors
- Clear `node_modules` and reinstall: `rm -rf node_modules && npm install`
- Clear Vite cache: `npm run build -- --force`

### Database Migration Issues
- Run migrations individually to identify issues
- Check Supabase logs for detailed error messages

## Contributing

1. Create a feature branch: `git checkout -b feature/your-feature`
2. Commit changes: `git commit -am 'Add feature'`
3. Push to branch: `git push origin feature/your-feature`
4. Submit a pull request

## License

MIT License - feel free to use this project for personal or commercial purposes.

## Support

For issues and questions:
1. Check existing issues on GitHub
2. Review Supabase documentation at https://supabase.com/docs
3. Create a new issue with detailed description

## Deployment

### Deploy to Vercel

```bash
npx vercel
```

### Deploy to Netlify

```bash
npm run build
# Drag and drop the 'dist' folder to Netlify
```

### Deploy to GitHub Pages

Update `vite.config.ts` with your repository name and run:

```bash
npm run build
git subtree push --prefix dist origin gh-pages
```

## Future Enhancements

- [ ] LinkedIn integration for auto-filling applications
- [ ] Email notifications for upcoming interviews
- [ ] AI-powered resume suggestions
- [ ] Salary trend analysis
- [ ] Interview preparation materials
- [ ] Referral tracking
- [ ] Mock interview scheduling
- [ ] Company research integration


