# URL Shortener Web App

A modern, user-friendly URL shortener application built with React and Next.js that provides core URL shortening functionality with analytical insights and custom shortcode support.

![URL Shortener Demo](https://drive.google.com/file/d/1IhS3Do5okBS2IkjS7tfSkscvToodBdLl/view?usp=sharing)

## 🚀 Features

### Core Functionality
- **URL Shortening**: Convert long URLs into short, memorable links
- **Custom Shortcodes**: Optional user-provided shortcodes (3-20 characters, alphanumeric)
- **Automatic Expiration**: Default 30-minute validity with customizable duration
- **Unique Link Generation**: Ensures all generated short codes are unique
- **Smart Redirection**: Client-side routing with countdown timer

### Analytics & Insights
- **Real-time Analytics**: Track total URLs, clicks, active/expired links
- **Individual Link Stats**: Monitor performance of each shortened URL
- **Recent Activity**: Overview of latest shortening activity
- **Click Tracking**: Detailed click count for each link

### User Experience
- **Responsive Design**: Optimized for desktop, tablet, and mobile devices
- **Intuitive Interface**: Clean, modern UI with tabbed navigation
- **Copy to Clipboard**: One-click copying of shortened URLs
- **Toast Notifications**: Real-time feedback for user actions
- **Accessibility**: Screen reader friendly with proper ARIA labels

### Technical Features
- **Comprehensive Logging**: Middleware for tracking all user interactions
- **Error Handling**: Robust validation and error messaging
- **Performance Optimized**: Built with React best practices
- **Type Safety**: Full TypeScript implementation

## 🛠️ Tech Stack

- **Frontend**: React 18, Next.js 14 (App Router)
- **Styling**: Tailwind CSS, shadcn/ui components
- **Icons**: Lucide React
- **Language**: TypeScript
- **State Management**: React Hooks (useState, useEffect)
- **Routing**: Next.js App Router
- **UI Components**: Radix UI primitives

## 📋 Requirements

- Node.js 18.0 or higher
- npm or yarn package manager
- Modern web browser with JavaScript enabled

## 🚀 Quick Start

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/url-shortener-app.git
cd url-shortener-app
```

### 2. Install Dependencies

```bash
npm install
# or
yarn install
```

### 3. Run Development Server

```bash
npm run dev
# or
yarn dev
```

### 4. Open in Browser

Navigate to [http://localhost:3000](http://localhost:3000) to see the application.

## 📁 Project Structure

```
url-shortener-app/
├── app/
│   ├── [shortCode]/
│   │   └── page.tsx          # Dynamic route for URL redirection
│   ├── globals.css           # Global styles and Tailwind CSS
│   ├── layout.tsx            # Root layout component
│   ├── loading.tsx           # Loading component
│   └── page.tsx              # Main application page
├── components/
│   └── ui/                   # shadcn/ui components
│       ├── button.tsx
│       ├── card.tsx
│       ├── input.tsx
│       ├── label.tsx
│       ├── tabs.tsx
│       ├── badge.tsx
│       └── toaster.tsx
├── hooks/
│   ├── use-mobile.tsx        # Mobile detection hook
│   └── use-toast.ts          # Toast notification hook
├── lib/
│   └── utils.ts              # Utility functions
├── public/                   # Static assets
├── .gitignore
├── next.config.js
├── package.json
├── tailwind.config.js
├── tsconfig.json
└── README.md
```

## 🎯 Usage Guide

### Shortening a URL

1. **Navigate to the "Shorten URL" tab**
2. **Enter the original URL** in the input field
3. **Optional**: Provide a custom shortcode (3-20 characters, alphanumeric only)
4. **Optional**: Set custom validity period (default: 30 minutes)
5. **Click "Shorten URL"** to generate the short link

### Managing Links

1. **Go to the "Manage Links" tab** to view all your shortened URLs
2. **Copy links** using the copy button next to each URL
3. **Open links** using the external link button
4. **View statistics** including click count and expiration time
5. **Monitor status** with active/expired badges

### Viewing Analytics

1. **Switch to the "Analytics" tab** for comprehensive insights
2. **Overview cards** show total URLs, clicks, active/expired counts
3. **Recent activity** displays your latest shortening activity
4. **Real-time updates** reflect current usage statistics

### Accessing Shortened URLs

- **Direct access**: Visit `yourdomain.com/[shortcode]` to be redirected
- **Countdown timer**: 5-second countdown before automatic redirection
- **Manual redirect**: Option to redirect immediately
- **Error handling**: Clear messages for expired or invalid links

## ⚙️ Configuration

### Environment Variables

Create a `.env.local` file in the root directory for environment-specific settings:

```env
# Application Settings
NEXT_PUBLIC_APP_URL=http://localhost:3000
NEXT_PUBLIC_DEFAULT_VALIDITY=30

# Analytics (Optional)
NEXT_PUBLIC_ANALYTICS_ID=your-analytics-id
```

### Customization Options

#### Default Validity Period
Modify the default expiration time in `app/page.tsx`:

```typescript
const [validityMinutes, setValidityMinutes] = useState(30) // Change default here
```

#### Short Code Length
Adjust the generated short code length in the `generateShortCode` function:

```typescript
for (let i = 0; i < 6; i++) { // Change length here
  result += chars.charAt(Math.floor(Math.random() * chars.length))
}
```

#### Custom Styling
Modify `tailwind.config.js` to customize the color scheme and styling:

```javascript
theme: {
  extend: {
    colors: {
      primary: "your-custom-color",
      // Add more custom colors
    }
  }
}
```

## 🚀 Deployment

### Deploy to Vercel (Recommended)

1. **Push your code to GitHub**
2. **Visit [vercel.com](https://vercel.com)**
3. **Import your repository**
4. **Deploy with default settings**

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/your-username/url-shortener-app)

### Deploy to Netlify

1. **Build the application**:
   ```bash
   npm run build
   ```

2. **Deploy the `out` folder to Netlify**

### Deploy to GitHub Pages

1. **Add to `next.config.js`**:
   ```javascript
   const nextConfig = {
     output: 'export',
     trailingSlash: true,
     images: {
       unoptimized: true
     }
   }
   ```

2. **Build and deploy**:
   ```bash
   npm run build
   ```

## 🔧 Development

### Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run start` - Start production server
- `npm run lint` - Run ESLint

### Adding New Features

1. **Create feature branch**: `git checkout -b feature/new-feature`
2. **Make changes** and test thoroughly
3. **Commit changes**: `git commit -m "Add new feature"`
4. **Push branch**: `git push origin feature/new-feature`
5. **Create pull request**

### Code Style

This project uses:
- **TypeScript** for type safety
- **Tailwind CSS** for styling
- **ESLint** for code linting
- **Prettier** for code formatting

## 🐛 Troubleshooting

### Common Issues

**Issue**: Links not redirecting properly
**Solution**: Ensure the short code exists and hasn't expired

**Issue**: Custom shortcode rejected
**Solution**: Verify it's 3-20 characters, alphanumeric only, and unique

**Issue**: Analytics not updating
**Solution**: Check browser local storage and refresh the page

**Issue**: Build errors
**Solution**: Clear `.next` folder and `node_modules`, then reinstall dependencies

