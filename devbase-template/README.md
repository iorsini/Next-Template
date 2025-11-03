# 🚀 DevBase Template

A complete, production-ready Next.js starter template with authentication, user management, and modern UI.

## ✨ Features

### Authentication
- 🔐 Email/Password authentication with bcrypt
- 🔑 OAuth integration (GitHub & Google)
- 🔄 Session management with NextAuth.js
- 🛡️ Protected routes with middleware

### User Management
- 👤 User profile with avatar upload (Cloudinary)
- ⚙️ Account settings (name, email, password)
- 🗑️ Account deletion
- 📧 Email uniqueness validation

### UI/UX
- 🎨 Modern, responsive design with Tailwind CSS
- 🌙 Dark theme optimized
- 📱 Mobile-first approach
- ♿ Accessible components
- 🎭 Loading states and error handling
- ✨ Smooth animations and transitions

### Developer Experience
- 📦 Clean, modular code structure
- 🔧 Reusable UI components
- 📝 TypeScript-ready
- 🚀 API Routes for backend logic
- 🔄 Hot reload in development

## 🛠️ Tech Stack

- **Framework:** Next.js 16
- **UI:** React 18, Tailwind CSS
- **Authentication:** NextAuth.js
- **Database:** MongoDB with Mongoose
- **File Upload:** Cloudinary
- **Icons:** Lucide React

## 📋 Prerequisites

- Node.js 20.9.0 or higher
- MongoDB instance (local or Atlas)
- Cloudinary account (for avatar uploads)
- GitHub OAuth app (optional)
- Google OAuth app (optional)

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone <your-repo-url>
cd devbase-template
```

### 2. Install dependencies

```bash
npm install
```

### 3. Set up environment variables

Copy `.env.example` to `.env.local`:

```bash
cp .env.example .env.local
```

Fill in your environment variables:

```env
# MongoDB
MONGODB_URI=mongodb://localhost:27017/devbase-template

# NextAuth
NEXTAUTH_URL=http://localhost:3000
NEXTAUTH_SECRET=generate-with-openssl-rand-base64-32

# OAuth (optional)
GITHUB_ID=your-github-client-id
GITHUB_SECRET=your-github-client-secret
GOOGLE_CLIENT_ID=your-google-client-id
GOOGLE_CLIENT_SECRET=your-google-client-secret

# Cloudinary
CLOUDINARY_CLOUD_NAME=your-cloud-name
CLOUDINARY_API_KEY=your-api-key
CLOUDINARY_API_SECRET=your-api-secret
```

### 4. Generate NextAuth Secret

```bash
openssl rand -base64 32
```

### 5. Run the development server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## 📁 Project Structure

```
devbase-template/
├── src/
│   ├── app/
│   │   ├── (auth)/           # Authentication pages
│   │   │   ├── login/
│   │   │   └── register/
│   │   ├── dashboard/         # Protected pages
│   │   │   ├── home/
│   │   │   ├── profile/
│   │   │   ├── settings/
│   │   │   └── about/
│   │   ├── api/              # API routes
│   │   │   ├── auth/
│   │   │   └── users/
│   │   ├── layout.js
│   │   ├── page.js
│   │   └── providers.js
│   ├── components/
│   │   ├── auth/             # Auth forms
│   │   ├── profile/          # Profile components
│   │   └── ui/               # Reusable UI components
│   ├── lib/                  # Utilities
│   │   ├── mongodb.js
│   │   ├── mongodbClient.js
│   │   └── cloudinary.js
│   └── models/               # MongoDB models
│       └── User.js
├── public/                   # Static files
├── middleware.js             # Route protection
└── tailwind.config.js
```

## 🔧 Configuration

### MongoDB Setup

**Local MongoDB:**
```env
MONGODB_URI=mongodb://localhost:27017/devbase-template
```

**MongoDB Atlas:**
1. Create a cluster at [mongodb.com/atlas](https://www.mongodb.com/atlas)
2. Get your connection string
3. Replace `<password>` with your database password
```env
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/dbname
```

### OAuth Setup

**GitHub OAuth:**
1. Go to [GitHub Settings > Developer Settings](https://github.com/settings/developers)
2. Create a new OAuth App
3. Set Homepage URL: `http://localhost:3000`
4. Set Authorization callback URL: `http://localhost:3000/api/auth/callback/github`
5. Copy Client ID and generate Client Secret

**Google OAuth:**
1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project
3. Enable Google+ API
4. Create OAuth 2.0 credentials
5. Add authorized redirect URI: `http://localhost:3000/api/auth/callback/google`

### Cloudinary Setup

1. Sign up at [cloudinary.com](https://cloudinary.com/)
2. Go to Dashboard
3. Copy Cloud Name, API Key, and API Secret

## 📝 API Routes

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/logout` - Logout user
- `GET/POST /api/auth/[...nextauth]` - NextAuth endpoints

### User Management
- `GET /api/users/me` - Get current user
- `PUT /api/users/me` - Update user profile
- `DELETE /api/users/me` - Delete user account
- `POST /api/users/me/avatar` - Upload avatar
- `DELETE /api/users/me/avatar` - Remove avatar

## 🎨 Customization

### Colors

Edit `tailwind.config.js`:

```javascript
colors: {
  primary: '#0B111c',    // Main background
  secondary: '#1e2939',  // Card background
  accent: '#00c951',     // Brand color
}
```

### Components

All UI components are in `src/components/ui/`:
- `Button.jsx` - Button with variants
- `Input.jsx` - Input with icons
- `Alert.jsx` - Alert messages
- `LoadingSpinner.jsx` - Loading indicator
- `Textarea.jsx` - Textarea input
- `AlertModal.jsx` - Modal for alerts
- `ConfirmModal.jsx` - Confirmation modal

## 🔒 Security Features

- Password hashing with bcrypt
- Protected routes with middleware
- Session-based authentication
- CSRF protection
- XSS prevention
- SQL injection prevention (NoSQL)

## 📱 Responsive Design

The template is fully responsive:
- Mobile: < 768px
- Tablet: 768px - 1024px
- Desktop: > 1024px

## 🚀 Deployment

### Vercel (Recommended)

1. Push your code to GitHub
2. Import project in [Vercel](https://vercel.com)
3. Add environment variables
4. Deploy!

### Other Platforms

The app can be deployed to:
- Railway
- Render
- DigitalOcean App Platform
- AWS Amplify
- Netlify (with serverless functions)

## 🤝 Contributing

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🙏 Acknowledgments

- Next.js team for the amazing framework
- Vercel for hosting
- Tailwind CSS for the utility-first CSS framework
- NextAuth.js for authentication
- MongoDB for the database
- Cloudinary for image hosting

## 📧 Support

If you have any questions or need help, please open an issue or contact the maintainer.

---

Made with ❤️ by Isadora