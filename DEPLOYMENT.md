# CareConnect Deployment Guide

## Prerequisites Checklist

- [ ] Supabase project created
- [ ] OpenAI API key obtained
- [ ] Stripe account setup
- [ ] WhatsApp Business API configured (optional)
- [ ] Domain name registered (for production)

## Step 1: Supabase Setup

### 1.1 Create Supabase Project
1. Go to [supabase.com](https://supabase.com)
2. Create a new project
3. Note your project URL and anon key

### 1.2 Run Database Schema
1. Navigate to SQL Editor in Supabase dashboard
2. Copy contents from `supabase/schema.sql`
3. Execute the SQL script
4. Verify all tables are created

### 1.3 Configure Storage
1. Go to Storage in Supabase dashboard
2. Create buckets:
   - `medical-records` (private)
   - `avatars` (public)
   - `prescriptions` (private)
3. Set up RLS policies for each bucket

### 1.4 Authentication Setup
1. Enable Email/Password authentication
2. Configure email templates
3. Set up OAuth providers (optional):
   - Google
   - Apple
   - Microsoft

## Step 2: Environment Configuration

Create `.env` file with production values:

```env
VITE_SUPABASE_URL=https://your-project.supabase.co
VITE_SUPABASE_ANON_KEY=your-anon-key
VITE_OPENAI_API_KEY=sk-your-openai-key
VITE_STRIPE_PUBLIC_KEY=pk_live_your-stripe-key
VITE_WHATSAPP_BUSINESS_ID=your-business-id
VITE_WHATSAPP_ACCESS_TOKEN=your-access-token
VITE_APP_URL=https://yourdomain.com
```

## Step 3: Build Application

```bash
npm install
npm run build
```

## Step 4: Deploy to Netlify

### Option A: Deploy via Netlify CLI

```bash
npm install -g netlify-cli
netlify login
netlify init
netlify deploy --prod
```

### Option B: Deploy via Git

1. Push code to GitHub/GitLab
2. Connect repository to Netlify
3. Configure build settings:
   - Build command: `npm run build`
   - Publish directory: `dist`
4. Add environment variables in Netlify dashboard
5. Deploy

## Step 5: Deploy to Vercel

```bash
npm install -g vercel
vercel login
vercel --prod
```

Or connect via Vercel dashboard:
1. Import Git repository
2. Configure project settings
3. Add environment variables
4. Deploy

## Step 6: Configure Custom Domain

### Netlify
1. Go to Domain settings
2. Add custom domain
3. Configure DNS records
4. Enable HTTPS

### Vercel
1. Go to Project Settings > Domains
2. Add domain
3. Configure DNS
4. HTTPS is automatic

## Step 7: Backend API Setup (Optional)

For production, create serverless functions for:
- Stripe webhooks
- WhatsApp webhooks
- OpenAI proxy (to hide API key)

### Netlify Functions

Create `netlify/functions/` directory:

```javascript
// netlify/functions/create-payment-intent.js
exports.handler = async (event) => {
  // Stripe payment logic
}

// netlify/functions/whatsapp-webhook.js
exports.handler = async (event) => {
  // WhatsApp webhook logic
}
```

### Vercel API Routes

Create `api/` directory:

```javascript
// api/create-payment-intent.js
export default async function handler(req, res) {
  // Stripe payment logic
}
```

## Step 8: Configure Webhooks

### Stripe Webhooks
1. Go to Stripe Dashboard > Developers > Webhooks
2. Add endpoint: `https://yourdomain.com/api/stripe-webhook`
3. Select events to listen for
4. Add webhook secret to environment variables

### WhatsApp Webhooks
1. Configure webhook URL in Meta Developer Console
2. Set verify token
3. Subscribe to message events

## Step 9: SSL/TLS Configuration

- Netlify/Vercel provide automatic HTTPS
- Ensure all API calls use HTTPS
- Configure HSTS headers

## Step 10: Performance Optimization

### Enable Caching
```javascript
// netlify.toml
[[headers]]
  for = "/assets/*"
  [headers.values]
    Cache-Control = "public, max-age=31536000, immutable"
```

### Enable Compression
- Netlify/Vercel enable Brotli/Gzip automatically

### Configure CDN
- Static assets are automatically served via CDN

## Step 11: Monitoring & Analytics

### Setup Error Tracking
```bash
npm install @sentry/react
```

### Configure Analytics
- Google Analytics
- Plausible (privacy-friendly)
- Supabase Analytics

## Step 12: HIPAA Compliance

### Required Steps
1. Sign BAA (Business Associate Agreement) with:
   - Supabase
   - Any third-party services handling PHI
2. Enable audit logging
3. Configure data retention policies
4. Implement data backup strategy
5. Setup incident response plan

### Security Headers

Add to `netlify.toml` or `vercel.json`:

```toml
[[headers]]
  for = "/*"
  [headers.values]
    X-Frame-Options = "DENY"
    X-Content-Type-Options = "nosniff"
    Referrer-Policy = "strict-origin-when-cross-origin"
    Permissions-Policy = "camera=(), microphone=(), geolocation=()"
    Content-Security-Policy = "default-src 'self'; script-src 'self' 'unsafe-inline'; style-src 'self' 'unsafe-inline';"
```

## Step 13: Testing Production

### Checklist
- [ ] Test user registration
- [ ] Test login/logout
- [ ] Test appointment booking
- [ ] Test video calls
- [ ] Test payment processing
- [ ] Test file uploads
- [ ] Test on mobile devices
- [ ] Test PWA installation
- [ ] Verify HIPAA compliance
- [ ] Load testing

## Step 14: Backup Strategy

### Database Backups
- Supabase provides automatic daily backups
- Configure point-in-time recovery

### Storage Backups
- Enable versioning on storage buckets
- Setup automated backups to external storage

## Troubleshooting

### Common Issues

**Build Fails**
- Check Node.js version (18+)
- Clear node_modules and reinstall
- Verify all environment variables

**API Errors**
- Check CORS configuration
- Verify API keys
- Check rate limits

**Authentication Issues**
- Verify Supabase URL and keys
- Check RLS policies
- Verify email templates

## Maintenance

### Regular Tasks
- Monitor error logs
- Review security alerts
- Update dependencies monthly
- Backup verification
- Performance monitoring
- HIPAA compliance audits

## Support

For deployment issues:
- Check deployment logs
- Review Netlify/Vercel documentation
- Contact support@careconnect.com

---

Last Updated: January 2024
