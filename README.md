# Nearby-Bazar# 🛒 Nearby Bazar - Complete E-Commerce Platform

## 📋 Overview
Nearby Bazar is a modern, secure, and feature-rich local commerce platform connecting customers with nearby shops. Built with vanilla JavaScript and Firebase for real-time functionality.

---

## ✨ What's New in V2

### 🔐 **SECURITY IMPROVEMENTS**
1. **Admin Authentication** - Password-protected admin panel
2. **Shop Authentication** - Secure login/registration with password hashing
3. **Firebase Security Rules** - Production-ready database rules
4. **Input Sanitization** - XSS protection on all user inputs
5. **Phone Validation** - Proper Indian phone number validation
6. **Rate Limiting** - Client-side request throttling

### 🐛 **BUG FIXES**
1. ✅ Fixed Firebase initialization issues
2. ✅ Fixed cart not clearing between shops
3. ✅ Fixed location detection auto-trigger
4. ✅ Fixed UPI payment flow (order saves before redirect)
5. ✅ Fixed negative stock issues
6. ✅ Fixed real-time order status updates
7. ✅ Fixed sidebar overlay z-index conflicts
8. ✅ Fixed order history pagination
9. ✅ Fixed menu category grouping
10. ✅ Fixed delivery charge calculation

### 🚀 **NEW FEATURES**

#### **User App**
- 🎨 Modern redesigned UI with better UX
- 📍 Auto location detection
- 🔍 Distance-based shop sorting
- 🛒 Persistent cart (localStorage)
- 📦 Real-time order tracking
- 📜 Complete order history
- 🎯 Empty states with helpful messages
- 🔔 Toast notifications
- ✨ Success animations
- 📱 Better mobile responsiveness

#### **Shop App**
- 🔐 Secure authentication system
- 📊 Live statistics dashboard
- 🔔 Real-time order notifications
- 🔊 Sound alerts for new orders
- 📋 Order status management (Pending → Cooking → Ready → Completed)
- 🍽️ Complete menu management
- 📷 Image support for menu items
- 📦 Stock tracking
- ⚙️ Delivery settings
- 💰 Delivery charge configuration
- 📈 Today's sales analytics
- 🎵 Toggle sound notifications

#### **Admin Panel**
- 🔐 Password-protected access
- 📊 Platform-wide statistics
- ✅ Shop approval system
- 🚫 Shop suspension/activation
- 🔍 Search functionality
- 📱 Real-time updates
- 🎨 Professional dashboard design

---

## 🏗️ File Structure

```
nearby-bazar-v2/
│
├── user.html              # Customer interface
├── shop.html              # Vendor dashboard
├── admin.html             # Admin console
├── firestore.rules        # Firebase security rules
└── README.md              # This file
```

---

## 🚀 Setup Instructions

### **1. Firebase Setup**

1. Go to [Firebase Console](https://console.firebase.google.com/)
2. Create a new project or use existing one
3. Enable Firestore Database
4. Enable Authentication (Phone Auth)
5. Copy your Firebase config

### **2. Update Firebase Config**

Update the `firebaseConfig` in all three HTML files:

```javascript
const firebaseConfig = {
    apiKey: "YOUR_API_KEY",
    authDomain: "YOUR_PROJECT.firebaseapp.com",
    projectId: "YOUR_PROJECT_ID",
    storageBucket: "YOUR_PROJECT.firebasestorage.app",
    messagingSenderId: "YOUR_SENDER_ID",
    appId: "YOUR_APP_ID"
};
```

### **3. Deploy Security Rules**

1. Go to Firestore Database → Rules
2. Copy content from `firestore.rules`
3. Publish the rules

### **4. Change Admin Password**

In `admin.html`, update the admin credentials:

```javascript
const ADMIN_CREDENTIALS = {
    username: "admin",
    password: "YOUR_SECURE_PASSWORD_HERE"  // CHANGE THIS!
};
```

### **5. Deploy Files**

Upload all HTML files to your web hosting:
- Firebase Hosting
- Netlify
- Vercel
- GitHub Pages
- Any static hosting

### **6. Enable HTTPS**

🚨 **IMPORTANT**: Always use HTTPS in production for security.

---

## 👥 User Roles & Access

### **Customer (user.html)**
- Browse nearby shops
- View menus
- Place orders
- Track order status
- View order history
- No authentication required (just name + phone)

### **Vendor (shop.html)**
- **Registration**: Self-registration with approval workflow
- **Login**: Shop ID + Password
- Manage menu items
- Accept/reject orders
- Update order status
- View analytics
- Configure delivery settings

### **Admin (admin.html)**
- **Login**: Username + Password
- Approve/reject shop registrations
- Suspend/activate shops
- View platform statistics
- Monitor all shops

---

## 🔒 Security Features

### **Authentication**
- ✅ Admin password protection
- ✅ Shop password hashing (SHA-256)
- ✅ Auto-logout on invalid sessions
- ✅ Session persistence with localStorage

### **Data Protection**
- ✅ Firebase Security Rules
- ✅ Input sanitization (XSS prevention)
- ✅ HTML escaping on all outputs
- ✅ Phone number validation
- ✅ SQL injection prevention (Firestore)

### **Access Control**
- ✅ Role-based permissions
- ✅ Shop-specific data isolation
- ✅ Customer order privacy
- ✅ Admin-only approval system

---

## 📱 Features Breakdown

### **Customer Features**
| Feature | Status |
|---------|--------|
| Browse shops | ✅ |
| Distance sorting | ✅ |
| Menu browsing | ✅ |
| Cart management | ✅ |
| Multiple payment modes | ✅ |
| Order tracking | ✅ |
| Order history | ✅ |
| Shop filtering | ✅ |
| Location detection | ✅ |

### **Shop Features**
| Feature | Status |
|---------|--------|
| Authentication | ✅ |
| Menu management | ✅ |
| Order notifications | ✅ |
| Order status updates | ✅ |
| Live statistics | ✅ |
| Delivery settings | ✅ |
| Sound alerts | ✅ |
| Stock management | ✅ |

### **Admin Features**
| Feature | Status |
|---------|--------|
| Secure login | ✅ |
| Shop approvals | ✅ |
| Shop suspension | ✅ |
| Platform stats | ✅ |
| Shop search | ✅ |
| Real-time updates | ✅ |

---

## 🎨 Design Features

- **Dark Theme** - Modern dark UI
- **Responsive** - Works on all devices
- **Animations** - Smooth transitions
- **Empty States** - Helpful placeholders
- **Loading States** - Clear feedback
- **Toast Notifications** - Non-intrusive alerts
- **Modal Dialogs** - Context-aware popups
- **Custom Scrollbars** - Aesthetic scrolling

---

## 🔧 Configuration Options

### **Shop Settings**
```javascript
{
  deliveryCharge: 0,        // In rupees
  minOrder: 0,              // Minimum order amount
  freeDeliveryAbove: 0      // Free delivery threshold
}
```

### **Menu Item Structure**
```javascript
{
  name: "Item Name",
  price: 100,               // In rupees
  category: "Category",
  stock: 50,                // Optional
  image: "url",             // Optional
  available: true
}
```

### **Order Status Flow**
```
pending → cooking → ready → completed
        ↓
    rejected
```

---

## 🐛 Known Limitations

1. **Client-side validation only** - Add server-side validation for production
2. **Basic password hashing** - Use bcrypt in production
3. **No email verification** - Add email/SMS OTP for better security
4. **No image upload** - Currently uses URLs only
5. **No payment gateway** - Only UPI deep linking
6. **No analytics backend** - Stats calculated client-side

---

## 📈 Future Enhancements

### **High Priority**
- [ ] Backend API with proper authentication
- [ ] Image upload to Firebase Storage
- [ ] SMS/Email OTP verification
- [ ] Payment gateway integration
- [ ] Push notifications
- [ ] Chat support system

### **Medium Priority**
- [ ] Order cancellation
- [ ] Rating & review system
- [ ] Coupon management
- [ ] Referral system
- [ ] Multiple language support
- [ ] Advanced analytics

### **Low Priority**
- [ ] Dark/Light theme toggle
- [ ] Voice ordering
- [ ] Scheduled orders
- [ ] Subscription plans
- [ ] Social media integration

---

## 🧪 Testing Guide

### **User Flow**
1. Open `user.html`
2. Enter name and phone
3. Browse shops
4. Add items to cart
5. Checkout with address
6. Track order status

### **Shop Flow**
1. Open `shop.html`
2. Register new shop
3. Wait for admin approval
4. Login with Shop ID
5. Add menu items
6. Accept incoming orders
7. Update order status

### **Admin Flow**
1. Open `admin.html`
2. Login with credentials
3. Approve pending shops
4. Monitor active shops
5. Suspend misbehaving shops

---

## 🚨 Production Checklist

Before going live:

- [ ] Change admin password
- [ ] Deploy Firebase Security Rules
- [ ] Enable HTTPS
- [ ] Add proper error logging
- [ ] Set up Firebase Authentication
- [ ] Configure Firebase App Check
- [ ] Add rate limiting (Cloud Functions)
- [ ] Set up monitoring/analytics
- [ ] Add terms & privacy policy
- [ ] Test on multiple devices
- [ ] Load testing
- [ ] Security audit

---

## 📞 Support & Issues

For bugs or feature requests:
1. Check existing documentation
2. Review Firebase console for errors
3. Check browser console for JavaScript errors
4. Verify Firebase rules are deployed

---

## 📄 License

This project is for educational purposes. Modify as needed for your use case.

---

## 👨‍💻 Developer Notes

### **Key Technologies**
- **Frontend**: Vanilla JavaScript, Tailwind CSS
- **Backend**: Firebase Firestore
- **Authentication**: Custom (upgrade to Firebase Auth recommended)
- **Real-time**: Firestore onSnapshot listeners
- **Notifications**: Browser Notifications API (future)

### **Code Structure**
- **No framework dependencies** - Pure JavaScript
- **CDN resources** - No build process needed
- **Real-time updates** - Firebase listeners
- **Client-side routing** - Single-page app pattern
- **Modular functions** - Easy to maintain

### **Performance Tips**
- Use Firestore indexes for large datasets
- Implement pagination for order history
- Cache static data with Service Worker
- Lazy load images
- Debounce search inputs

---

## 🎯 Key Improvements from V1

| Aspect | V1 | V2 |
|--------|----|----|
| Security | ❌ No auth | ✅ Full auth |
| XSS Protection | ❌ Vulnerable | ✅ Sanitized |
| Admin Panel | ❌ No protection | ✅ Password protected |
| UI/UX | ⚠️ Basic | ✅ Modern |
| Error Handling | ❌ Minimal | ✅ Comprehensive |
| Mobile Support | ⚠️ OK | ✅ Optimized |
| Real-time | ✅ Yes | ✅ Enhanced |
| Documentation | ❌ None | ✅ Complete |

---

## 🌟 Credits

**Designed & Developed by**: Your Team
**Version**: 2.0
**Last Updated**: February 2026

---

**Happy Coding! 🚀**
