# localist.ai - MVP Product Requirements Document
## Contract-Ready Specification for Development Completion


## 1. EXECUTIVE SUMMARY

### 1.1 Product Vision
localist.ai is the "Spotify of where to eat & drink" — an AI-powered discovery platform that unifies local dining and nightlife exploration through curated "Best-Of" lists, personalized recommendations, and social sharing features.

### 1.2 Business Model
- **Consumer:** Freemium subscription ($25?/month for AI Concierge features)
- **Merchant:** List placement fees Birthday Loyalty Program
- **Data:** Consumer Search Intelligence (CSI) reports for businesses
- **API:** White-label content syndication

### 1.3 Target Market Launch
**Priority Cities? (MVP):** New York City, Los Angeles, Chicago, Miami, Las Vegas

---

## 2. MVP SCOPE DEFINITION

### Foundation
✅ **Database Schema:** PostgreSQL with users, cities, venues, lists, favorites, sessions, interactions  
✅ **Backend API:** Express.js with authentication, cities, venues, lists, search, recommendations  
✅ **Frontend Framework:** Next.js 15 with TypeScript, Tailwind CSS, shadcn/ui components  
✅ **Infrastructure:** Docker Compose for local development, AWS deployment scripts  
✅ **Authentication:** JWT-based auth with bcrypt password hashing  
✅ **Recommendation Engine:** Basic collaborative and content-based filtering framework  


## 3. CORE DELIVERABLES

### **MODULE 1: Consumer Discovery Experience**

#### 1.1 Home & Navigation 
**Acceptance Criteria:**
- [ ] Landing page with city grid (5 cities minimum)
- [ ] City detail pages with featured "Best-Of" lists
- [ ] Responsive design (mobile, tablet, desktop)
- [ ] SEO meta tags and social sharing previews

**Components Required:**
- City selection grid with images and venue counts
- City hero sections with descriptions
- Featured lists carousel
- Search bar with city context


#### 1.2 Browsing & Filtering 
**Acceptance Criteria:**
- [ ] Filter by Cuisine, Signature Dish, Vibe, Price Range
- [ ] Neighborhood filter within city view
- [ ] Toggle between Cuisine view, Signature Dish view, Custom Lists view
- [ ] Filter state persists in URL for sharing

#### 1.3 Best-Of Lists (Curated Content)
**Acceptance Criteria:**
- [ ] Display curated lists organized by city
- [ ] List categories: Cuisine, Occasions, Signature Dishes, Vibe
- [ ] List detail page shows all venues with images
- [ ] Share functionality for lists

**List Categories to Include:**
- **Cuisine:** Best Pizza, Best Tacos, Best Sushi, Best Italian, etc.
- **Occasions:** Date Night, Walk-In Friendly, Late Night, Brunch
- **Signature Dishes:** Best Burger, Best Cocktails, Best Desserts
- **Vibe:** Romantic, Casual, Upscale, Hidden Gems

#### 1.4 Venue Cards & Details 
**Acceptance Criteria:**
- [ ] Venue card displays: image, name, category, price, rating
- [ ] Venue detail page includes: full description, address, phone, hours, website
- [ ] Google Maps integration showing location
- [ ] "Save to List" button with dropdown (Favorites, Create New, Add to Existing)
- [ ] "Similar Venues" recommendations section
- [ ] Social sharing buttons

#### 1.5 Sample Itineraries Loaded
**Acceptance Criteria:**
- [ ] Get preset curated itineraries by city and vibe from David
- [ ] Display format: Day-by-day breakdown with venues
- [ ] Free tier: View preset itineraries only
- [ ] Paid tier: Custom AI-generated itineraries (behind paywall)
- [ ] "Coming Soon" placeholder for custom itinerary builder

**Preset Itinerary Examples:**
- "NYC Weekend Food Tour" (3 days)
- "LA Cocktail Crawl" (1 day)
- "Miami Beach Dining Guide" (2 days)

### **MODULE 2: User System**

#### 2.1 User Authentication
**Acceptance Criteria:**
- [ ] Email/password registration with validation
- [ ] Login with "Remember Me" option
- [ ] Logout functionality
- [ ] Password reset flow (email-based)
- [ ] Session persistence across browser sessions
- [ ] JWT token refresh before expiry

**Security Requirements:**
- Password: minimum 8 characters, mixed case, numbers
- Email validation and uniqueness check
- Rate limiting: 5 login attempts per 15 minutes
- Secure password hashing (bcrypt, 10 rounds)

#### 2.2 User Roles & Access Tiers
**Acceptance Criteria:**
- [ ] Anonymous: Can view lists, venues, cities (no save/create)
- [ ] Registered (Free): Can save venues, create/share lists
- [ ] Paid Subscriber: Custom itineraries, AI concierge, advanced features

#### 2.3 User Dashboard
**Acceptance Criteria:**
- [ ] "My Lists" section showing user-created lists
- [ ] "Saved Venues" grid with favorited venues
- [ ] "My Itineraries" (placeholder for future)
- [ ] Account settings: profile, preferences, privacy
- [ ] Activity overview: stats for lists created, venues saved

#### 2.4 Preferences & Onboarding 
**Acceptance Criteria:**
- [ ] Initial onboarding flow (5-7 questions)
- [ ] Preference categories: cuisines, price range, dietary restrictions
- [ ] Visual progress indicator for onboarding
- [ ] Preferences influence AI recommendations
- [ ] Can update preferences from dashboard

**Onboarding Questions:**
1. What cities are you interested in?
2. What's your typical budget for dining? ($, $$, $$$, $$$$)
3. Favorite cuisines? (Multi-select)
4. Any dietary restrictions? (Vegetarian, Vegan, Gluten-free, etc.)
5. What are you looking for? (Date Night, Quick Bite, Fine Dining, etc.)

### **MODULE 3: List Management System**

#### 3.1 Custom List Creation 
**Acceptance Criteria:**
- [ ] Create new list with name and description
- [ ] Add/remove venues from list
- [ ] Drag-and-drop venue reordering
- [ ] Set list as Public or Private
- [ ] Delete list functionality
- [ ] Duplicate/clone list feature


#### 3.2 List Sharing 
**Acceptance Criteria:**
- [ ] Generate shareable public URL for any list
- [ ] Public lists viewable without login
- [ ] "Clone this list" button for logged-in users
- [ ] Social sharing buttons (Facebook, Twitter, Email, Copy Link)
- [ ] Share modal with preview

**Sharing URL Format:**
```
https://discoverlocal.ai/lists/share/[list-id]
```

#### 3.3 List Discovery 
**Acceptance Criteria:**
- [ ] Browse public lists by city
- [ ] Filter lists by category
- [ ] Search lists by name/description
- [ ] Display list creator name and venue count
- [ ] "Trending Lists" section (most viewed/saved)

### **MODULE 4: Search & Discovery**

#### 4.1 Advanced Search 
**Acceptance Criteria:**
- [ ] Search across venues and lists
- [ ] Real-time search suggestions (autocomplete)
- [ ] Filter search results by city, cuisine, price, rating
- [ ] Search results show relevance score
- [ ] Recent searches history (stored locally)

#### 4.2 AI Recommendations 
**Acceptance Criteria:**
- [ ] Personalized recommendations based on user behavior
- [ ] Collaborative filtering ("Users like you also liked...")
- [ ] Content-based filtering (similar venues)
- [ ] Trending venues by city
- [ ] Recommendation explanations ("Because you saved...")
- [ ] "Refresh Recommendations" button

**Recommendation Algorithms:**
1. **Collaborative Filtering:** User-item interaction matrix
2. **Content-Based:** Venue similarity (cuisine, price, location, features)
3. **Trending:** Popular venues based on recent interactions

---

#### 4.3 User Interaction Tracking
**Acceptance Criteria:**
- [ ] Track venue views with duration
- [ ] Track saves, shares, list additions
- [ ] Track search queries
- [ ] Store interaction context (source, time, device)
- [ ] Privacy-compliant data collection
- [ ] Use interactions to improve recommendations

### **MODULE 5: Merchant Revenue Tools**

#### 5.1 Happy Hour / Limited Time Offers 
**Acceptance Criteria:**
- [ ] Dedicated "Happy Hour" list per city
- [ ] Merchant upload form: image, hours, description, menu
- [ ] Payment integration: $25?/event or $300?/year (3 events/month)
- [ ] Admin approval workflow
- [ ] Display special offer badge on venue cards

#### 5.2 Pop-Up Events List 
**Acceptance Criteria:**
- [ ] "Pop-Ups" list for each city
- [ ] Merchant submission form (similar to Happy Hour)
- [ ] Time-limited display (auto-remove after event date)

### **MODULE 6: Content Management & Admin**

#### 6.1 Admin Dashboard 
**Acceptance Criteria:**
- [ ] Password-protected admin portal
- [ ] Create/edit/delete cities, venues, lists
- [ ] Approve merchant submissions (Happy Hour, Pop-Ups)
- [ ] View analytics: user count, venue saves, list creations
- [ ] Manual override for featured content

**Admin Capabilities:**
- CRUD operations for all content entities
- Bulk upload venues via CSV
- Feature/unfeature lists
- User management (view, disable accounts)
- Basic reporting dashboard

#### 6.2 Content Ingestion System 
**Acceptance Criteria:**
- [ ] CSV upload for bulk venue import
- [ ] Data validation and error reporting
- [ ] Support for venue metadata (hours, features, coordinates)
- [ ] Image upload and optimization
- [ ] Content review queue

### **MODULE 7: Integration & Data Partners**

#### 7.1 DDD (Diners, Drive-Ins & Dives) Integration 
**Acceptance Criteria:**
- [ ] Display DDD featured venues with special badge
- [ ] Link to DDD episode/content
- [ ] Searchable map of DDD venues
- [ ] API integration or manual data import


#### 7.2 Events & Concerts Integration [LOW PRIORITY]
**Acceptance Criteria:**
- [ ] "Watch The Game" list (weekly updated)
- [ ] Display sporting events and venue suggestions
- [ ] "Events & Concerts" list per city
- [ ] Link to ticket purchasing (DraftKings, Live Nation affiliates?)

#### 7.3 Google Maps API 
**Acceptance Criteria:**
- [ ] Display venue locations on interactive map
- [ ] Distance calculation from user location
- [ ] Directions link to Google/Apple Maps
- [ ] Map clustering for list views


### **MODULE 8: Growth & Viral Features**

#### 8.1 Social Sharing 
**Acceptance Criteria:**
- [ ] Share lists via: Link copy, Facebook, Twitter, Email
- [ ] Open Graph meta tags for rich previews
- [ ] Share modal with preview card
- [ ] Track share events for analytics

### **MODULE 9: Security & Compliance**

#### 9.1 Authentication Security 
**Acceptance Criteria:**
- [ ] JWT tokens with 7-day expiry
- [ ] Refresh token rotation
- [ ] Rate limiting on auth endpoints (5 attempts/15 min)
- [ ] Password reset with expiring email tokens
- [ ] Session invalidation on logout

#### 9.2 Data Privacy 
**Acceptance Criteria:**
- [ ] GDPR-compliant data collection
- [ ] Privacy policy and terms of service pages
- [ ] User data export functionality
- [ ] Account deletion with complete data removal
- [ ] Cookie consent banner (EU compliance)

#### 9.3 Input Validation & Security 
**Acceptance Criteria:**
- [ ] SQL injection prevention (parameterized queries)
- [ ] XSS prevention (input sanitization)
- [ ] CSRF protection (SameSite cookies)
- [ ] Security headers (Helmet.js)
- [ ] HTTPS enforcement

## 4. DATA REQUIREMENTS

### 4.1 Minimum Content for Launch
**Per City:**
- [ ] 100+ verified venues with complete information
- [ ] 15+ curated "Best-Of" lists
- [ ] 5+ signature dish lists
- [ ] 3+ vibe/occasion lists

**Total MVP Content:**
- [ ] 500+ venues across 5 cities
- [ ] 75+ curated lists
- [ ] All venues have: name, address, category, price, image, description
- [ ] All lists have: name, description, 15-25 venues, cover image

### 4.2 Data Sources & Collection
**Content Gathering Methods:**
- [ ] Manual curation from trusted sources (Eater, Infatuation, Thrillist, Yelp)
- [ ] Google Maps API for basic venue data
- [ ] Perplexity AI for venue descriptions and recommendations
- [ ] Web scraping (ethical, robots.txt compliant)

## 5. TECHNICAL SPECIFICATIONS

### 5.1 Technology Stack (Fixed)
**Frontend:**
- Next.js 15, React 18, TypeScript
- Tailwind CSS, shadcn/ui

**Backend:**
- Node.js 20, Express.js, TypeScript
- PostgreSQL 15, Redis 7
- JWT authentication, bcrypt

**Infrastructure:**
- AWS: ECS Fargate, RDS, ElastiCache, S3, CloudFront
- Docker for containerization
- GitHub Actions for CI/CD

### 5.2 Database Schema
**Core Tables:**
- `users` - User accounts and preferences
- `cities` - City information and metadata
- `venues` - Venue details and features
- `lists` - Curated "Best-Of" lists
- `user_lists` - User-created lists
- `user_favorites` - Saved venues
- `user_sessions` - Active sessions
- `user_interactions` - Tracking for recommendations

### 5.3 API Endpoints 
**Authentication:** `/api/auth/*`  
**Cities:** `/api/cities/*`  
**Venues:** `/api/venues/*`  
**Lists:** `/api/lists/*`  
**User:** `/api/user/*`  
**Search:** `/api/search`  
**Recommendations:** `/api/recommendations/*`


## 6. DELIVERABLES CHECKLIST

### 6.1 Code Deliverables
- [ ] Frontend application (Next.js) - production build
- [ ] Backend API (Express.js) - production build
- [ ] Database migrations (PostgreSQL)
- [ ] Docker configurations (docker-compose.yml)
- [ ] AWS deployment scripts (CDK or Terraform)
- [ ] Environment configuration templates (.env.example)

---

### 6.2 Documentation Deliverables
- [ ] API documentation (OpenAPI/Swagger)
- [ ] Setup instructions (README.md)
- [ ] Deployment guide
- [ ] Admin user guide
- [ ] Codebase architecture documentation
- [ ] Database schema documentation


## 7. ACCEPTANCE CRITERIA

### 7.1 Functional Acceptance
The MVP is considered complete when:
1. All features are implemented and functional
2. All core user flows work end-to-end:
   - Anonymous user browses cities and lists
   - User registers and saves venues to favorites
   - User creates a custom list and shares it
   - User receives personalized recommendations
3. All initial launch cities have minimum content requirements met
4. Admin can manage content via dashboard

---

### 7.2 Technical Acceptance
The MVP passes technical acceptance when:
1. All API endpoints return correct responses
2. Frontend is responsive on mobile, tablet, desktop
3. Application deploys successfully to AWS production

### 7.3 Content Acceptance
Content is considered complete when:
1. App has 100+ venues with complete data
2. Each city has 1+ curated lists
3. All venues have verified information and images
4. All lists have descriptions and proper categorization

**Key Pages Required:**
1. Home / Landing Page
2. City Selection Page
3. City Detail Page (with lists)
4. List Detail Page (venues in list)
5. Venue Detail Page
6. User Dashboard
7. Search Results Page
8. Login / Registration Pages
9. User Settings / Preferences
10. Admin Dashboard

### Appendix: API Endpoint Summary

**Authentication:**
- `POST /api/auth/register`
- `POST /api/auth/login`
- `POST /api/auth/logout`
- `GET /api/auth/me`

**Cities:**
- `GET /api/cities`
- `GET /api/cities/:cityId`
- `GET /api/cities/:cityId/venues`
- `GET /api/cities/:cityId/lists`

**Venues:**
- `GET /api/venues/:venueId`
- `GET /api/venues/:venueId/similar`

**Lists:**
- `GET /api/lists`
- `GET /api/lists/:listId`

**User (Protected):**
- `GET /api/user/profile`
- `PUT /api/user/profile`
- `PUT /api/user/preferences`
- `GET /api/user/lists`
- `POST /api/user/lists`
- `PUT /api/user/lists/:listId`
- `DELETE /api/user/lists/:listId`
- `GET /api/user/favorites`
- `POST /api/user/favorites/:venueId`
- `DELETE /api/user/favorites/:venueId`

**Search:**
- `GET /api/search?q=...&city=...&cuisine=...&price=...`

**Recommendations:**
- `GET /api/recommendations/personalized?cityId=...`
- `GET /api/recommendations/trending?cityId=...`
- `POST /api/recommendations/track`

