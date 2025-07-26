# VendorConnect - Street Food Supply Chain Platform

A comprehensive platform connecting street food vendors with verified suppliers in India. Built with Next.js, TypeScript, and Tailwind CSS.

## 🚀 Features

### For Vendors (Street Food Sellers)

#### **Category-Based Product Browsing**
- Browse products by categories: Food Items, Clothing, Snacks, Drinks, Spices, Equipment, Packaging, and more
- Visual category selection with icons and descriptions
- Filter products by subcategories within each main category

#### **Location-Based Shop Discovery**
- Automatic location detection using browser geolocation
- Find nearby suppliers within a specified radius
- Shop ratings, business hours, and verification status
- Distance calculation and sorting by proximity

#### **Enhanced Shopping Experience**
- Advanced search functionality across products and shops
- Shopping cart with quantity management
- Real-time price calculations
- Product tags and detailed descriptions
- Minimum order requirements and stock availability

#### **Order Management & Tracking**
- Comprehensive order tracking with status updates
- Real-time order status: Pending → Confirmed → Shipped → Delivered
- Order history with detailed information
- SMS notifications for order updates
- Payment status tracking

#### **Live Updates & Animations**
- Smooth animations using Framer Motion
- Real-time order status updates
- Loading states and progress indicators
- Interactive UI elements with hover effects

### For Suppliers

#### **Shop Management**
- Complete shop profile management
- Business hours, address, and contact information
- Category selection for shop specialization
- Verification status and rating display

#### **Product Management**
- Add, edit, and remove products
- Set pricing, minimum orders, and stock levels
- Product categorization and tagging
- Availability status management

#### **Order Processing**
- Real-time order notifications
- Order status management workflow
- SMS notifications to vendors
- Payment status tracking

#### **Analytics Dashboard**
- Revenue tracking and analytics
- Customer count and order statistics
- Product performance metrics
- Pending payment monitoring

### **SMS Integration**
- Automated SMS notifications for order updates
- Customizable message templates
- Integration with phone number: +91 9130050207
- Order confirmation, shipping, and delivery notifications

## 🛠️ Technology Stack

- **Frontend**: Next.js 14, React 18, TypeScript
- **Styling**: Tailwind CSS, Framer Motion
- **State Management**: React Hooks
- **Notifications**: React Hot Toast
- **Icons**: Lucide React
- **SMS Service**: Custom SMS service (configurable for Twilio, AWS SNS, etc.)

## 📱 Key Features Implementation

### Location Services
```typescript
// Automatic location detection
navigator.geolocation.getCurrentPosition(
  (position) => {
    const { latitude, longitude } = position.coords
    const nearby = getNearbyShops(latitude, longitude, 15)
  }
)
```

### Category-Based Browsing
```typescript
// Product filtering by category
const categoryProducts = getProductsByCategory(selectedCategory)
const shopProducts = getProductsByShop(selectedShop.id)
```

### SMS Notifications
```typescript
// Automated SMS sending
await smsService.sendSMS({
  to: order.vendorPhone,
  from: '+91 9130050207',
  body: message
})
```

### Order Tracking
```typescript
// Real-time status updates
const orderStatuses = ['pending', 'confirmed', 'shipped', 'delivered']
const currentStep = getStatusStep(order.status)
```

## 🏗️ Project Structure

```
hackathon/
├── app/
│   ├── page.tsx                 # Enhanced landing page with categories
│   ├── vendor/
│   │   ├── dashboard/           # Category-based browsing & location services
│   │   ├── orders/             # Order tracking with live updates
│   │   ├── login/
│   │   └── register/
│   └── supplier/
│       ├── dashboard/          # Shop management & analytics
│       ├── login/
│       └── register/
├── lib/
│   ├── demo-data.ts            # Comprehensive product & shop data
│   └── sms.ts                  # SMS service integration
└── components/                 # Reusable UI components
```

## 🚀 Getting Started

1. **Install Dependencies**
   ```bash
   npm install
   ```

2. **Run Development Server**
   ```bash
   npm run dev
   ```

3. **Open Browser**
   Navigate to `http://localhost:3000`

## 📊 Demo Data

The platform includes comprehensive demo data:

- **8 Item Categories**: Food, Clothing, Snacks, Drinks, Spices, Equipment, Packaging, Other
- **8 Shop Locations**: Realistic Mumbai-area locations with coordinates
- **12 Products**: Various items across different categories
- **Sample Orders**: Complete order history with tracking

## 🔧 Configuration

### SMS Service
Configure your SMS provider in `lib/sms.ts`:
```typescript
// Replace with your SMS service (Twilio, AWS SNS, etc.)
this.apiKey = process.env.SMS_API_KEY || 'demo-key'
this.fromNumber = process.env.SMS_FROM_NUMBER || '+91 9130050207'
```

### Location Services
Default location coordinates (Mumbai) in `lib/demo-data.ts`:
```typescript
const defaultLocation = { lat: 19.0760, lng: 72.8777 }
```

## 🎨 UI/UX Features

- **Responsive Design**: Mobile-first approach
- **Dark/Light Mode**: Automatic theme detection
- **Smooth Animations**: Framer Motion integration
- **Loading States**: Skeleton screens and spinners
- **Interactive Elements**: Hover effects and transitions
- **Accessibility**: ARIA labels and keyboard navigation

## 📱 Mobile Features

- **Touch-Friendly**: Optimized for mobile devices
- **Location Services**: GPS integration for nearby shops
- **SMS Integration**: Direct phone number integration
- **Responsive Layout**: Adaptive design for all screen sizes

## 🔒 Security Features

- **User Authentication**: Session management
- **Data Validation**: Input sanitization
- **Secure SMS**: Encrypted communication
- **Location Privacy**: User consent for location access

## 🚀 Deployment

### Vercel (Recommended)
```bash
npm run build
vercel --prod
```

### Environment Variables
```env
SMS_API_KEY=your_sms_api_key
SMS_FROM_NUMBER=+91 9130050207
```

## 📈 Future Enhancements

- **Real-time Chat**: Vendor-supplier communication
- **Payment Integration**: Online payment processing
- **Inventory Management**: Real-time stock updates
- **Analytics Dashboard**: Advanced business insights
- **Mobile App**: Native iOS/Android applications
- **AI Recommendations**: Smart product suggestions

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License.

## 📞 Support

For support and questions:
- Phone: +91 9130050207
- Email: support@vendorconnect.com

---

**VendorConnect** - Revolutionizing street food supply chain in India! 🍽️🚀 