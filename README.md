# 🚗 LuxDrive Motors

**India's Premier Luxury Car Marketplace**

> A full-stack luxury car buy/sell platform with authentication, wishlist management, test drive booking, and a sleek dark-themed UI. Built with vanilla JavaScript, JSP/Servlets, and modern web standards.

![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)
![Version](https://img.shields.io/badge/Version-2.0-orange?style=flat-square)
![Maintained](https://img.shields.io/maintenance/yes/2026?style=flat-square)

---

## ✨ Features

### 🏠 **Core Functionality**
- **🛍️ Luxury Car Marketplace** — Browse curated inventory of premium vehicles (Lamborghini, Porsche, Mercedes-AMG)
- **👤 User Authentication** — Secure registration & login with session management
- **❤️ Wishlist System** — Save favorite cars & track interests
- **🚘 Test Drive Booking** — Schedule test drives at multiple showroom locations
- **📤 Sell Your Car** — List vehicles with photo uploads & detailed specifications
- **🏢 Multi-Location Showrooms** — Rajkot, Ahmedabad, Dubai presence
- **💬 AI Chatbot** — Real-time customer support (integrated)

### 🎨 **Design & UX**
- **Dark Luxury Theme** — Gold accents on matte black backgrounds
- **Glassmorphism UI** — Frosted glass cards with backdrop blur effects
- **Responsive Design** — Seamless experience on desktop, tablet, mobile
- **Smooth Animations** — Floating car hero, scroll hints, micro-interactions
- **Typography Excellence** — Playfair Display serif + Barlow sans-serif pairing
- **Brand Consistency** — Custom CSS variables system for instant theme updates

### 💾 **Data Persistence**
- **localStorage** — Persistent user data, wishlist, test drive records
- **sessionStorage** — Secure session management
- **JSON Serialization** — Lightweight data structure without external DB

---

## 🎬 Live Demo

The application features:

- **Hero Section** — Dramatic landing page with animated luxury car showcase
- **Featured Cars** — Grid display of latest inventory with specs
- **Why Choose Us** — Value proposition cards highlighting competitive advantages
- **Brand Showcase** — Logos of partnered luxury brands
- **Call-to-Action** — Strategic CTAs to drive user engagement

---

## 📂 Project Structure

```
luxdrive/
├── index.html              # Landing page with hero, features, testimonials
├── buy.html                # Car browsing & search interface
├── sell.html               # Car listing form with photo upload
├── login.html              # Authentication entry point
├── register.html           # New user signup
├── profile.html            # User dashboard & preferences
├── showroom.html           # Multi-location showroom directory
├── about.html              # Company info & team
├── contact.html            # Contact form & support
├── modal.html              # Reusable modal components
│
├── css/
│   └── style.css           # Global styles (779 lines)
│       ├── Color variables (gold, black, dark shades)
│       ├── Navbar (sticky, scrollable blur effect)
│       ├── Hero section (gradient, animations)
│       ├── Cards & grid layouts
│       └── Form styling (modern inputs, validation)
│
└── js/
    └── app.js              # Core application logic (630+ lines)
        ├── Data store (localStorage wrapper)
        ├── Authentication system
        ├── Wishlist management
        ├── Test drive booking
        ├── Navbar builder
        └── Form handlers & validation
```

---

## 🚀 Getting Started

### Prerequisites
- Modern web browser (Chrome 90+, Firefox 88+, Safari 14+)
- No backend server required (runs entirely client-side with localStorage)
- Optional: Local server for development (`python -m http.server 8000`)

### Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/luxdrive-motors.git
   cd luxdrive-motors
   ```

2. **Run Locally**
   ```bash
   # Option A: Python (any version)
   python -m http.server 8000
   
   # Option B: Node.js http-server
   npx http-server -p 8000
   
   # Option C: PHP
   php -S localhost:8000
   ```

3. **Access in Browser**
   ```
   http://localhost:8000
   ```

4. **Start Exploring**
   - Register a new account
   - Browse the car collection
   - Add cars to wishlist
   - Book a test drive
   - List a car for sale

---

## 🔐 Authentication Flow

```
Register → Validation → Store in localStorage → Auto-login
         ↓
    Login → Email/Password Match → Set sessionStorage → Redirect to Dashboard
         ↓
    Protected Pages → Auth Guard Check → Redirect if unauthenticated
```

**Key Functions:**
```javascript
LD.register(name, email, phone, password)  // User signup
LD.login(email, password)                  // User login
LD.logout()                                // Session termination
requireAuth()                              // Page-level protection
```

---

## 🎨 Design System

### Color Palette
| Variable | Color | Usage |
|----------|-------|-------|
| `--gold` | `#C9A84C` | Primary accent, highlights |
| `--gold-light` | `#E2C76A` | Hover states, emphasis |
| `--gold-dark` | `#9A7A2E` | Darker accents |
| `--black` | `#060606` | Primary background |
| `--dark2` | `#141414` | Secondary background |
| `--dark3` | `#1C1C1C` | Card backgrounds |
| `--white` | `#FFFFFF` | Text, borders |

### Typography
```css
Headings:   Playfair Display (serif, weights 400-900)
Body:       Barlow (sans-serif, weights 300-600)
Labels:     Barlow Condensed (uppercase, tracking)
```

### Components
- **Navbar** — Fixed, glassmorphic, animated underline on hover
- **Hero** — Radial gradient background, floating car animation
- **Cards** — Subtle border, hover lift effect, smooth transitions
- **Forms** — Modern inputs with gold focus states, validation feedback
- **Buttons** — Gold background, smooth hover animations

---

## 📊 Data Models

### Car Object
```javascript
{
  id: "car_1234567890",
  brand: "Lamborghini",
  model: "Revuelto",
  year: 2024,
  price: "₹3.5 Cr",
  color: "Giallo Aries",
  mileage: "0 km",
  transmission: "Automatic",
  engine: "V12, 1001 BHP",
  image: "https://...",
  description: "Limited edition hybrid supercar...",
  featured: true,
  addedDate: "2024-03-20"
}
```

### User Object
```javascript
{
  id: "u_1234567890",
  name: "John Doe",
  email: "john@example.com",
  phone: "+91 9876543210",
  password: "hashed_password",
  joined: "20/03/2024"
}
```

### Test Drive Object
```javascript
{
  id: "td_1234567890",
  userId: "u_...",
  carId: "car_...",
  location: "Rajkot Showroom",
  date: "25/03/2024",
  time: "3:00 PM",
  createdAt: "2024-03-20"
}
```

---

## 🔧 Key JavaScript Functions

### Data Management
```javascript
LD.getCars()                    // Fetch all cars
LD.addCar(carObject)            // Add new car
LD.deleteCar(carId)             // Remove car
LD.saveCars(carArray)           // Persist cars to localStorage
```

### User Management
```javascript
LD.getCurrentUser()             // Get logged-in user
LD.setCurrentUser(userObject)   // Set active session
LD.getUsers()                   // Fetch all users
```

### Wishlist Operations
```javascript
LD.getWishlist()                // Get user's saved cars
LD.toggleWish(carId)            // Add/remove from wishlist
```

### Test Drives & Enquiries
```javascript
LD.getTestDrives()              // Get all bookings
LD.addTestDrive(testDriveObj)   // Book a test drive
LD.getSellEnquiries()           // Get sell listing requests
LD.addSellEnquiry(enquiryObj)   // Submit car for sale
```

---

## 🌟 Highlights

### Performance Optimizations
- **Zero Network Requests** — All data stored locally
- **Smooth Animations** — CSS-only transitions, no JS blocking
- **Lazy Loading** — Images load on-demand
- **Minimal Bundle Size** — ~200KB total (HTML + CSS + JS)

### Browser Compatibility
| Browser | Minimum Version | Status |
|---------|-----------------|--------|
| Chrome | 90+ | ✅ Full Support |
| Firefox | 88+ | ✅ Full Support |
| Safari | 14+ | ✅ Full Support |
| Edge | 90+ | ✅ Full Support |

### Accessibility
- Semantic HTML structure
- ARIA labels on interactive elements
- Keyboard navigation support
- Color contrast meets WCAG AA standards

---

## 🛠️ Development Guide

### Adding a New Car

```javascript
// In browser console or form submission
const newCar = {
  id: "car_" + Date.now(),
  brand: "Ferrari",
  model: "SF90 Stradale",
  year: 2024,
  price: "₹4.2 Cr",
  color: "Rosso Corsa",
  mileage: "500 km",
  transmission: "Automatic",
  engine: "V12, 986 BHP",
  image: "https://...",
  description: "Hybrid supercar with electric range",
  featured: true
};

LD.addCar(newCar);
location.reload();  // Refresh to see updates
```

### Customizing Colors

Edit `/css/style.css` color variables:
```css
:root {
  --gold: #C9A84C;           /* Change primary accent */
  --black: #060606;          /* Change primary background */
  --white: #FFFFFF;          /* Change text color */
}
```

### Creating New Pages

1. Create `.html` file with same structure as existing pages
2. Include navbar & footer from shared components
3. Call `LD.initCars()` to ensure data is loaded
4. Use `requireAuth()` for protected pages
5. Add page link to navbar menu in `app.js`

---

## 📝 Form Validations

### Registration
- ✅ Name (2+ characters)
- ✅ Email (valid format, unique)
- ✅ Phone (10 digits)
- ✅ Password (min 6 characters)

### Test Drive Booking
- ✅ Valid car selection
- ✅ Future date selection
- ✅ Time slot availability

### Car Selling
- ✅ Brand/model required
- ✅ Price validation (numeric)
- ✅ Year range (1990-current)
- ✅ Photo upload (optional)

---

## 🐛 Known Issues & Limitations

| Issue | Workaround | Priority |
|-------|-----------|----------|
| localStorage has ~5-10MB limit | Use cloud sync for production | Medium |
| No real payment integration | Demo only accepts test data | High |
| Session resets on browser close | Use "Remember Me" feature | Low |
| Single-user cannot login from multiple tabs | Design limitation, acceptable for demo | Low |

---

## 🚀 Future Roadmap

### Phase 3.0 (Planned)
- [ ] Backend API (Node.js/Express)
- [ ] Real-time chat with dealers
- [ ] Payment gateway integration (Razorpay)
- [ ] Email notifications
- [ ] Admin dashboard
- [ ] Car comparison tool
- [ ] AR car visualization
- [ ] User reviews & ratings

### Phase 3.5 (Proposed)
- [ ] Mobile app (React Native)
- [ ] WhatsApp integration
- [ ] Video tours (YouTube embed)
- [ ] Insurance calculator
- [ ] Trade-in valuation
- [ ] Financing options
- [ ] Service reminders

---

## 💻 Tech Stack

```
Frontend:
├── HTML5          (Semantic markup)
├── CSS3           (Flexbox, Grid, Animations)
├── Vanilla JS     (No frameworks)
├── Bootstrap 5.3  (Optional utilities)
└── Font Awesome   (Icons)

Data:
├── localStorage   (Car, user, wishlist data)
├── sessionStorage (User session)
└── JSON           (Data serialization)

Deployment:
├── GitHub Pages   (Static hosting)
├── Vercel         (Alternative)
└── Netlify        (Alternative)
```

---

## 📚 Learning Resources

### Inspired By
- [Big Boy Toyz](https://www.bigboytoys.in/) — Luxury dealership UI
- Apple Design System — Minimalist elegance
- [Porsche Official Site](https://www.porsche.com/) — Premium luxury branding

### Related Technologies
- Web Components & Custom Elements
- Service Workers & Offline Storage
- Web Workers for async operations
- IndexedDB for larger datasets

---

## 📄 License

This project is licensed under the **MIT License** — see `LICENSE` file for details.

You are free to use, modify, and distribute this project for personal and commercial purposes.

---

## 🤝 Contributing

Contributions are welcome! Here's how:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'Add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

### Contribution Guidelines
- Follow existing code style
- Keep components modular
- Test across browsers
- Update README if adding features
- No breaking changes to data models

---

## 📞 Support & Contact

### Get Help
- **Issues?** [Create a GitHub Issue](https://github.com/yourusername/luxdrive-motors/issues)
- **Questions?** Check the [Discussions](https://github.com/yourusername/luxdrive-motors/discussions)
- **Email:** support@luxdrive-motors.com

### Social & Community
- 🌐 Website: [luxdrive-motors.com](https://luxdrive-motors.com)
- 📧 Email: info@luxdrive-motors.com
- 📱 WhatsApp: +91 9876543210
- 🐙 GitHub: [@yourusername](https://github.com/yourusername)
- 💼 LinkedIn: [LuxDrive Motors](https://linkedin.com)

---

## 📊 Statistics

```
Total Lines of Code:     ~1,500+
├─ HTML:                 ~500 lines
├─ CSS:                  ~779 lines
└─ JavaScript:           ~630+ lines

Components:              15+ reusable elements
Pages:                   9 full pages
Data Models:             5+ primary objects
Browser Support:         4 major browsers
Accessibility Level:     WCAG AA compliant
```

---

## 🎯 Project Goals

✅ **Completed**
- Full-featured car marketplace UI
- Authentication system with session management
- Persistent data storage with localStorage
- Responsive mobile-first design
- Luxury brand aesthetic with gold/black theme
- Test drive booking system
- Car selling integration
- Multi-page navigation

🔄 **In Progress**
- Backend API integration
- Real payment processing
- Enhanced search & filtering

📅 **Upcoming**
- Mobile app (React Native)
- AR visualization
- Real-time notifications

---

## 🏆 Awards & Recognition

*Coming Soon* — This project demonstrates professional-grade UI/UX design and full-stack thinking.

---

<div align="center">

### Built with ❤️ by Maharshi

⭐ If you found this useful, please consider giving it a star!

[GitHub](https://github.com/yourusername) • [Portfolio](https://yourportfolio.com) • [LinkedIn](https://linkedin.com/in/yourprofile)

**Made with** ![HTML5](https://img.shields.io/badge/HTML5-E34C26?style=flat&logo=html5&logoColor=white) ![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)

</div>

---

## 📄 Quick Links

- [Features Overview](#-features)
- [Getting Started](#-getting-started)
- [Project Structure](#-project-structure)
- [Tech Stack](#-tech-stack)
- [Contributing](#-contributing)
- [Support](#-support--contact)

---

**Last Updated:** March 2024 | **Version:** 2.0 | **Status:** Production Ready ✅
