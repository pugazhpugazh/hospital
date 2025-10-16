# CareConnect - Quick Start Guide

## 🚀 Get Started in 5 Minutes

### Step 1: Install Dependencies (1 min)
```bash
npm install
```

### Step 2: Setup Environment (2 min)

Create `.env` file in the root directory:

```env
# Supabase (Get from https://supabase.com)
VITE_SUPABASE_URL=https://your-project.supabase.co
VITE_SUPABASE_ANON_KEY=your-anon-key

# OpenAI (Get from https://platform.openai.com)
VITE_OPENAI_API_KEY=sk-your-key

# Stripe (Get from https://stripe.com)
VITE_STRIPE_PUBLIC_KEY=pk_test_your-key

# Optional: WhatsApp Business API
VITE_WHATSAPP_BUSINESS_ID=your-id
VITE_WHATSAPP_ACCESS_TOKEN=your-token

# App URL
VITE_APP_URL=http://localhost:5173
```

### Step 3: Setup Database (1 min)

1. Create a Supabase project at https://supabase.com
2. Go to SQL Editor
3. Copy and paste the contents of `supabase/schema.sql`
4. Click "Run"

### Step 4: Start Development Server (1 min)
```bash
npm run dev
```

Visit http://localhost:5173

## 🎯 Test the Application

### Create Test Users

**Patient Account:**
- Email: patient@test.com
- Password: Test123!@#
- Role: Patient

**Doctor Account:**
- Email: doctor@test.com
- Password: Test123!@#
- Role: Doctor

**Sales Account:**
- Email: sales@test.com
- Password: Test123!@#
- Role: Sales

**Admin Account:**
- Email: admin@test.com
- Password: Test123!@#
- Role: Admin

### Test Features

1. **Public Pages**
   - Visit landing page at `/`
   - Check About, Services, Contact pages

2. **Authentication**
   - Register a new account at `/register`
   - Login at `/login`

3. **Patient Portal** (`/patient`)
   - Book appointments
   - View medical records
   - Start telemedicine call
   - Manage prescriptions

4. **Doctor Portal** (`/doctor`)
   - View schedule
   - Manage patients
   - Conduct consultations

5. **Sales Portal** (`/sales`)
   - Manage leads
   - View analytics

6. **Admin Portal** (`/admin`)
   - User management
   - System analytics

## 🔧 Common Commands

```bash
# Development
npm run dev          # Start dev server
npm run build        # Build for production
npm run preview      # Preview production build
npm run lint         # Run ESLint

# Deployment
npm run build        # Build
# Then deploy 'dist' folder to Netlify/Vercel
```

## 📱 Progressive Web App

To test PWA features:
1. Build the app: `npm run build`
2. Preview: `npm run preview`
3. Open in Chrome
4. Click install icon in address bar

## 🐛 Troubleshooting

**Port 5173 already in use?**
```bash
# Kill the process or use different port
npm run dev -- --port 3000
```

**Build errors?**
```bash
# Clear cache and reinstall
rm -rf node_modules package-lock.json
npm install
```

**Supabase connection issues?**
- Verify your Supabase URL and anon key
- Check if project is paused (free tier)
- Ensure RLS policies are set up

**Can't access camera/microphone?**
- Use HTTPS or localhost
- Grant browser permissions
- Check browser compatibility

## 📚 Next Steps

1. **Customize Branding**
   - Update colors in `tailwind.config.js`
   - Replace logo in components
   - Modify content in public pages

2. **Configure Services**
   - Set up Stripe products
   - Configure WhatsApp templates
   - Customize AI prompts

3. **Deploy to Production**
   - Follow `DEPLOYMENT.md`
   - Set up custom domain
   - Configure SSL/HTTPS

## 🆘 Need Help?

- 📖 Read the full [README.md](README.md)
- 🚀 Check [DEPLOYMENT.md](DEPLOYMENT.md)
- 💬 Contact: support@careconnect.com

---

Happy coding! 🎉
