# Quantum Chain - Quick Start Guide

## 🚀 Get Started in 3 Steps

### 1. Start the Development Server

The server should already be running in a separate PowerShell window. If not:

```bash
cd C:\Users\siddh\OneDrive\Desktop\React\Gen2.0\sme_block\quantum-chain
npm run dev
```

### 2. Open the App

Navigate to: **http://localhost:3000**

### 3. Sign In

Click "Sign In" and use Privy to authenticate with:
- Email
- Wallet (MetaMask, WalletConnect, etc.)
- Google

## 📱 First Time Setup

1. **Sign Up**: Click "Sign Up" or "Sign In" (Privy handles both)
2. **Choose Method**: Select email, wallet, or Google
3. **Create Account**: Follow Privy's prompts
4. **Embedded Wallet**: Privy will create a wallet for you automatically
5. **Dashboard**: You'll be redirected to the dashboard

## 🎯 What You Can Do Now

### Inventory Management
- **Items**: Manage products with SKU, barcode, pricing
- **Warehouses**: Create and manage warehouse locations
- **Categories**: Organize items by category
- **Brands**: Track product brands
- **Units**: Define measurement units

### Navigation
- **Home**: Dashboard with sales activity and inventory summary
- **Inventory**: Full inventory management
- **Sales**: Sales orders, invoices, customers
- **Purchases**: Purchase orders, vendors, bills
- **Reports**: Analytics and reporting
- **Warehouses**: Warehouse management

## 🔑 Test Credentials

Since we're using Privy, you can sign in with:
- **Any email address** (Privy will send a magic link)
- **Any wallet** (MetaMask, WalletConnect, Coinbase Wallet, etc.)
- **Google account**

## 🛠️ Development Commands

```bash
# Start development server
npm run dev

# Build for production
npm run build

# Start production server
npm start

# Database commands
npm run db:push      # Push schema changes
npm run db:studio    # Open Drizzle Studio (database GUI)
npm run db:generate  # Generate migrations

# Code quality
npm run lint         # Run ESLint
npm run typecheck    # Run TypeScript checks
```

## 📊 Database Studio

To view and edit your database:

```bash
npm run db:studio
```

This opens Drizzle Studio at **http://localhost:4000**

## 🎨 Customization

### Change Theme
- Click the theme toggle in the header
- Supports light/dark mode

### Update Branding
Edit `src/config/site.ts`:
```typescript
export const siteConfig = {
  name: "Your App Name",
  description: "Your description",
  // ...
}
```

## 🔐 User Roles

Currently, all users are assigned the "user" role. To make someone an admin:

1. Open Drizzle Studio: `npm run db:studio`
2. Navigate to the `user` table
3. Find the user and change `role` to "admin"

## 🐛 Troubleshooting

### Port Already in Use
```bash
# Kill process on port 3000
npx kill-port 3000
npm run dev
```

### Database Connection Issues
- Check your `DATABASE_URI` in `.env`
- Make sure Neon database is accessible
- Run `npm run db:push` to sync schema

### Privy Authentication Issues
- Check `NEXT_PUBLIC_PRIVY_APP_ID` in `.env`
- Make sure you're using the correct App ID from Privy dashboard
- Clear browser cache and try again

### Build Errors
```bash
# Clean and rebuild
rm -rf .next
npm run build
```

## 📱 Mobile Testing

The app is responsive and works on mobile devices. To test:

1. Find your local IP: `ipconfig` (Windows) or `ifconfig` (Mac/Linux)
2. Update `NEXT_PUBLIC_APP_URL` in `.env` to your IP
3. Access from mobile: `http://YOUR_IP:3000`

## 🚀 Next: Add Blockchain Features

Ready to add supply chain tracking? Check out `INTEGRATION_GUIDE.md` for:
- Smart contract integration
- IPFS order storage
- Blockchain order tracking
- Gasless transactions

## 📚 Learn More

- **Privy Docs**: https://docs.privy.io/
- **Next.js Docs**: https://nextjs.org/docs
- **Drizzle ORM**: https://orm.drizzle.team/
- **shadcn/ui**: https://ui.shadcn.com/

## 💡 Tips

1. **Use Drizzle Studio** to explore your database visually
2. **Check the console** for helpful debug information
3. **Use the theme toggle** to switch between light/dark mode
4. **Explore all menu items** to see available features
5. **Check `MIGRATION_COMPLETE.md`** for detailed migration info

## 🎉 You're All Set!

Your Quantum Chain app is running with:
- ✅ Privy authentication
- ✅ Full inventory management
- ✅ Modern UI
- ✅ Database with Drizzle
- ✅ Ready for blockchain features

**Happy coding!** 🚀
