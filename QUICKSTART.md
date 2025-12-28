# Quick Start Guide

## ⚡ 5-Minute Setup

### Step 1: Install Dependencies
```bash
npm install
```

### Step 2: Configure Supabase
1. Go to https://supabase.com and create a free account
2. Create a new project
3. Copy your project URL and Anon Key from Settings > API
4. Create `.env.local` file:
   ```
   VITE_SUPABASE_URL=your_project_url
   VITE_SUPABASE_ANON_KEY=your_anon_key
   ```

### Step 3: Set Up Database
```bash
# Option A: Using Supabase CLI (if installed)
npx supabase link --project-ref your_project_ref
npx supabase db push

# Option B: Manual setup in Supabase Dashboard
# 1. Go to SQL Editor
# 2. Create new query
# 3. Copy and paste entire contents of: supabase/migrations/20240101000000_initial_schema.sql
# 4. Click "Run"
```

### Step 4: Start Development
```bash
npm run dev
```

### Step 5: Access Application
- Open http://localhost:5173
- Click "Sign up" to create account
- Start tracking your job applications!

---

## 📋 Project Overview

### What's Included

✅ Complete React + Vite setup
✅ TypeScript with strict mode
✅ TailwindCSS styling
✅ Supabase backend & auth
✅ 9 database tables with RLS
✅ 8 custom hooks
✅ 9 page components
✅ 6 component folders
✅ Utility libraries for dates, analytics, alerts
✅ Mobile responsive design
✅ Professional UI with Lucide icons

### Key Features

- 📊 **Dashboard**: Real-time metrics and analytics
- 📝 **Applications**: Kanban pipeline for job tracking
- 📅 **Calendar**: Schedule interviews and deadlines
- ⏱️ **Timer**: Pomodoro-style study sessions
- 📄 **Resume**: Upload and analyze resumes
- 🔗 **Integrations**: Connect LinkedIn and services
- 📱 **Mobile**: Fully responsive on all devices

---

## 🎯 First Steps

### 1. Create an Application Entry
- Go to Applications > New Application
- Fill in company name, role, and job details
- Click "Save Application"
- Application appears on pipeline board

### 2. Schedule a Interview
- Go to Calendar
- Click "+ Add Event"
- Select date and time
- Add company name and location
- Click "Add Event"

### 3. Start a Study Session
- Go to Timer
- Set duration (default 25 minutes)
- Click "Start"
- When done, click "Stop" → "Save Session"

### 4. Upload Your Resume
- Go to Resume
- Click upload area to select PDF
- Add analysis notes
- Click "Upload Resume"

---

## 🔧 Configuration Files

| File | Purpose |
|------|---------|
| `package.json` | Dependencies and scripts |
| `vite.config.ts` | Build configuration |
| `tsconfig.json` | TypeScript settings |
| `tailwind.config.ts` | Styling theme |
| `supabase/config.toml` | Supabase setup |
| `.env.local` | Environment variables (create this) |
| `.vscode/settings.json` | VS Code preferences |

---

## 💻 Available Commands

```bash
npm run dev           # Start dev server
npm run build         # Build for production
npm run lint          # Check code style
npm run type-check    # Check TypeScript
npm run preview       # Preview production build
```

---

## 🗂️ Project Structure at a Glance

```
Placementprep/
├── src/
│   ├── components/     # 6 folders of reusable components
│   ├── pages/          # 8 full-page components
│   ├── hooks/          # 5 custom React hooks
│   ├── lib/            # Utility functions
│   ├── types/          # TypeScript interfaces
│   ├── integrations/   # Supabase client & queries
│   ├── App.tsx         # Router & layout
│   ├── main.tsx        # Entry point
│   └── index.css       # Global styles
│
├── supabase/
│   ├── config.toml     # Configuration
│   └── migrations/     # Database schema
│
├── .vscode/            # VS Code settings
├── public/             # Static assets
├── README.md           # Full documentation
├── SETUP.md            # Setup checklist
├── package.json        # Dependencies
└── vite.config.ts      # Build config
```

---

## 🐛 Common Issues & Fixes

### "Module not found" error
```bash
npm install
```

### "VITE_SUPABASE_URL is undefined"
- Create `.env.local` file with Supabase credentials
- Restart dev server: `npm run dev`

### Database connection error
- Verify credentials in `.env.local` are correct
- Check Supabase project is active
- Run migrations from SQL editor

### Port 5173 already in use
```bash
npm run dev -- --port 5174
```

---

## 📚 Learn More

- [React Docs](https://react.dev) - Learn React
- [Vite Docs](https://vitejs.dev) - Learn Vite
- [TailwindCSS](https://tailwindcss.com) - Learn styling
- [Supabase Docs](https://supabase.com/docs) - Learn backend
- [TypeScript Docs](https://www.typescriptlang.org) - Learn TypeScript

---

## 🚀 Ready to Deploy?

### Vercel (Recommended)
```bash
npm install -g vercel
vercel
```

### Netlify
```bash
npm run build
# Drag 'dist' folder to Netlify
```

### GitHub Pages
```bash
npm run build
git subtree push --prefix dist origin gh-pages
```

---

## 💡 Pro Tips

1. **Type Safety**: Run `npm run type-check` before committing
2. **Code Quality**: `npm run lint` to check code style
3. **Hot Reload**: Dev server automatically reloads changes
4. **Browser DevTools**: React DevTools extension helpful
5. **Database**: Check Supabase Dashboard for data updates

---

## 🎓 What You Can Build

With this setup, you can:
- ✅ Track job applications and interview progress
- ✅ Manage study time with timer sessions
- ✅ Schedule interviews and deadlines
- ✅ Analyze resume keywords and formatting
- ✅ Get placement analytics and insights
- ✅ Export data for analysis
- ✅ Share progress with mentors

---

## 📞 Need Help?

1. Check README.md for detailed documentation
2. Review SETUP.md for troubleshooting
3. Check Supabase documentation
4. Review code comments in components
5. Check browser console for errors

---

**Happy tracking! 🎉**

Good luck with your placement preparation!
