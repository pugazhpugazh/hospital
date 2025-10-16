# CareConnect - Healthcare Management System

A comprehensive Progressive Web App (PWA) for unified healthcare management, connecting Patients, Doctors, Sales Teams, and Admins.

## 🚀 Features

### Core Functionality
- **Multi-Role Dashboards**: Separate portals for Patients, Doctors, Sales, and Admins
- **Telemedicine**: WebRTC-powered video consultations
- **Appointment Management**: AI-assisted booking via WhatsApp
- **Electronic Health Records**: Secure document storage and sharing
- **Prescription Management**: Digital prescriptions with refill tracking
- **Secure Messaging**: HIPAA-compliant communication

### Technology Stack
- **Frontend**: React 18 + Vite
- **Styling**: TailwindCSS + shadcn/ui
- **Backend**: Supabase (PostgreSQL + Auth + Storage)
- **AI**: OpenAI GPT-4o
- **Video**: WebRTC (Simple-Peer)
- **Payments**: Stripe
- **Messaging**: WhatsApp Business API
- **Security**: HIPAA-compliant with RLS policies

## 📋 Prerequisites

- Node.js 18+ and npm
- Supabase account
- OpenAI API key
- Stripe account
- WhatsApp Business API access (optional)

## 🛠️ Installation

1. **Clone the repository**
```bash
cd Healthcare
```

2. **Install dependencies**
```bash
npm install
```

3. **Environment Setup**

Create a `.env` file in the root directory:

```env
# Supabase Configuration
VITE_SUPABASE_URL=your_supabase_project_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key

# OpenAI Configuration
VITE_OPENAI_API_KEY=your_openai_api_key

# Stripe Configuration
VITE_STRIPE_PUBLIC_KEY=your_stripe_public_key

# WhatsApp Business API
VITE_WHATSAPP_BUSINESS_ID=your_whatsapp_business_id
VITE_WHATSAPP_ACCESS_TOKEN=your_whatsapp_access_token

# App Configuration
VITE_APP_URL=http://localhost:5173
```

4. **Database Setup**

- Go to your Supabase project
- Navigate to SQL Editor
- Run the schema from `supabase/schema.sql`

5. **Start Development Server**
```bash
npm run dev
```

The app will be available at `http://localhost:5173`

## 🏗️ Project Structure

```
Healthcare/
├── public/                 # Static assets
├── src/
│   ├── components/
│   │   ├── layout/        # Navbar, Footer, DashboardLayout
│   │   └── ui/            # shadcn/ui components
│   ├── lib/
│   │   ├── supabase.js    # Supabase client & auth
│   │   ├── ai.js          # OpenAI integration
│   │   ├── webrtc.js      # Video call manager
│   │   ├── whatsapp.js    # WhatsApp API
│   │   ├── stripe.js      # Payment processing
│   │   ├── security.js    # HIPAA compliance utilities
│   │   └── utils.js       # Helper functions
│   ├── pages/
│   │   ├── public/        # Landing, About, Services, Contact
│   │   ├── auth/          # Login, Register
│   │   └── portals/       # Patient, Doctor, Sales, Admin
│   ├── App.jsx            # Main app component
│   ├── main.jsx           # Entry point
│   └── index.css          # Global styles
├── supabase/
│   └── schema.sql         # Database schema
├── .env.example           # Environment variables template
├── package.json
├── vite.config.js
└── tailwind.config.js
```

## 👥 User Roles

### Patient Portal
- Book appointments
- Video consultations
- View medical records
- Manage prescriptions
- Track health metrics
- Secure messaging with doctors

### Doctor Portal
- Manage schedule
- Patient management
- Video consultations
- Create prescriptions
- Access patient records
- Performance analytics

### Sales Portal
- Lead management
- Sales pipeline tracking
- Analytics & reporting
- CRM functionality

### Admin Portal
- User management
- System analytics
- Security monitoring
- HIPAA compliance reports
- System settings

## 🔒 Security & Compliance

- **HIPAA Compliant**: Row-level security policies
- **End-to-End Encryption**: Secure data transmission
- **Audit Logging**: Complete access tracking
- **Session Management**: Auto-timeout for inactive sessions
- **Role-Based Access Control**: Granular permissions

## 🚀 Deployment

### Build for Production
```bash
npm run build
```

### Preview Production Build
```bash
npm run preview
```

### Deploy to Netlify/Vercel
1. Connect your repository
2. Set environment variables
3. Deploy with build command: `npm run build`
4. Output directory: `dist`

## 📱 Progressive Web App

The app is PWA-ready with:
- Offline support
- Install to home screen
- Push notifications (configurable)
- Service worker caching

## 🧪 Testing

```bash
# Run linter
npm run lint

# Type checking (if using TypeScript)
npm run type-check
```

## 🔧 Configuration

### Supabase Setup
1. Create tables using `supabase/schema.sql`
2. Enable Row Level Security
3. Configure Storage buckets for medical records
4. Set up authentication providers

### Stripe Setup
1. Create products and prices
2. Configure webhooks
3. Test with test mode keys

### WhatsApp Business API
1. Register business account
2. Get API credentials
3. Configure webhook endpoint

## 📚 API Documentation

### Supabase Tables
- `user_roles` - User role assignments
- `profiles` - User profiles
- `doctors` - Doctor information
- `appointments` - Appointment bookings
- `medical_records` - Patient records
- `prescriptions` - Medication prescriptions
- `messages` - Secure messaging
- `sales_leads` - Sales CRM
- `video_sessions` - Video call logs
- `health_metrics` - Patient vitals

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License.

## 🆘 Support

For support, email support@careconnect.com or join our Slack channel.

## 🎯 Roadmap

- [ ] Mobile apps (React Native)
- [ ] Advanced AI diagnostics
- [ ] Wearable device integration
- [ ] Multi-language support
- [ ] Pharmacy integration
- [ ] Insurance claim processing
- [ ] Lab results integration
- [ ] Appointment reminders via SMS

## 👏 Acknowledgments

- shadcn/ui for beautiful components
- Supabase for backend infrastructure
- OpenAI for AI capabilities
- Lucide for icons

---

Built with ❤️ by the CareConnect Team
