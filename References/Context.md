# Nely Mobile App - Comprehensive Project Context

## Project Vision & Mission

### Vision
Become Malaysia's most trusted family health coordination platform.

### Mission
Help Malaysian families keep track of their elderly parents' health, together.

### Value Proposition
"Finally, a simple way for the whole family to stay connected to mom and dad's health - whether you're in the same house or across the city."

---

## The Problem & Solution

### Core Problem
- Adult children worry about elderly parents living separately
- Hard to coordinate health information among family members
- Elderly forget to take medications or track their health
- Family members don't know when to worry or when things are fine

### Target Users (MVP Focus)
**Primary:** Malaysian families with elderly parents
- Adult children (20-50) with smartphones
- Elderly parents who may/may not use smartphones
- Focus: Lower/Middle-class families who can afford basic healthcare but want better coordination

---

## MVP Core Features (Keep It Simple)

### 1. Simple Health Tracking
- **Vital signs (BP, Spo2, Pulse, Temp, Glucose & Respiratory rate)**
- **Medication management**
- **Appointment management**
- **Notes**

**Input Methods:**
- Family members can enter for elderly
- Elderly can enter for themselves
- Photo evidence of vital signs readings

### 2. Family Groups (Up to 5 People)
- Create family group around 1 elderly person
- All family members see the same health data
- Simple roles: "admin", "carer" and "viewer"
- Everyone gets notifications for concerning readings

### 3. Smart Alerts (Simple Rules-Based)
- **Red Alert:** BP above 180/110, glucose above 250 → immediate attention needed
- **Yellow Alert:** Readings trending up, missed medications 2+ days
- **Green:** Everything normal

### 4. Basic Languages
- **Bahasa Malaysia** (essential)
- **English** (urban families)
- Simple interface that works for both languages

### What We're NOT Doing (At Launch)
❌ Multiple elderly per family  
❌ Healthcare provider integration  
❌ Mandarin/Tamil
❌ Rural offline mode
❌ Insurance partnerships
❌ Advanced AI insights  
❌ Community features  

---

## User Flows

### New User Flow (Create Family Group)
1. Splash screen
2. Welcome onboarding flow (5 slides)
3. Auth screen (user register for new account)
4. Verify screen (email verification), enter code from email sent
5. Boarding screen (option: 'create family group' or 'enter family code')
6. Create family group screen (if choosing to create family group)

### New User Flow (Join Existing Family)
1. Splash screen
2. Welcome onboarding flow (5 slides)
3. Auth screen (user register for new account)
4. Verify screen (email verification), enter code from email sent
5. Boarding screen (option: 'create family group' or 'enter family code')
6. Home screen (if choosing to enter existing family group code)

### Existing User Flow
1. Splash screen
2. Home screen

**Remark:** If existing user signs out, navigate to auth screen. If user closes app then reopens, flow is: splash screen → auth screen → home screen (no welcome onboarding). Welcome onboarding only shows after fresh install.

---

## UI/UX Design Philosophy

### Core Design Identity: Modern Healthcare App
**Visual Strategy:** Contemporary app design with healthcare reliability - moving beyond clinical minimalism to engaging, modern interface design.

**Design Pillars:**
- **Modern & Engaging:** Contemporary app aesthetics with smooth animations and interactions
- **Healthcare Trustworthy:** Professional reliability without sterile medical coldness
- **Malaysian Cultural:** Respectful family dynamics and local healthcare patterns
- **Multi-User Accessible:** Works for independent, dependent, and bedridden elderly users

### Background & Visual Design Evolution
- **Primary Background:** Gradient backgrounds and modern card designs instead of pure white
- **Card Backgrounds:** Glassmorphism with subtle color tints for visual interest
- **Color Temperature:** Warmer color palette balancing trust with approachability

---

## Color Palette System

### Brand Identity Colors

**Emerald Green (#10B981)**
- **Purpose:** Primary brand color, CTAs, success states, positive health indicators
- **Psychology:** Trust, growth, healing, natural wellness
- **Healthcare Context:** Associated with positive health outcomes and medical safety
- **Malaysian Cultural Fit:** Green symbolizes Islam, nature, and harmony in Malaysian culture
- **Usage:** Primary buttons, health confirmations, medication compliance, family activity success

**Ocean Blue (#0EA5E9)**
- **Purpose:** Secondary brand color, navigation, information states, data visualization
- **Psychology:** Reliability, professionalism, calm, stability
- **Healthcare Context:** Medical trust, clinical reliability, information clarity
- **Malaysian Cultural Fit:** Blue represents trust and stability, common in Malaysian healthcare
- **Usage:** Secondary buttons, navigation elements, charts, family member indicators

### Health Status Colors

**Success Green (#059669)**
- Normal vital signs (BP <140/90, normal glucose)
- Medication taken on time
- Healthy trend indicators
- Goal achievement celebrations

**Warning Amber (#D97706)**
- Concerning health readings (BP 140-159/90-99)
- Missed medication reminders
- Trend deterioration alerts
- Appointment reminders

**Critical Red (#DC2626)**
- Dangerous vital signs (BP >160/100, critical glucose)
- Emergency health alerts
- Severe medication non-compliance
- Urgent medical attention required

**Info Blue (#0284C7)**
- General health information
- Educational content
- Neutral notifications
- Family coordination updates

### Accessibility & Compliance

**WCAG AA Standards - Contrast Ratios:**
- Text on White: 21:1 (Exceeds AA standard of 4.5:1)
- Green on White: 4.5:1 (Meets AA standard)
- Blue on White: 7.1:1 (Exceeds AA standard)
- Red on White: 5.9:1 (Exceeds AA standard)
- Amber on White: 4.8:1 (Meets AA standard)

**Color Blindness Support:**
- Icons and text labels supplement color coding
- Multiple visual cues beyond color alone
- High contrast maintained across all color blindness types

### React Native Color Implementation

```javascript
export const colors = {
  // Brand Identity
  primary: '#10B981',      // Emerald Green
  secondary: '#0EA5E9',    // Ocean Blue
  
  // Health Status
  success: '#059669',      // Success Green
  warning: '#D97706',      // Warning Amber
  error: '#DC2626',        // Critical Red
  info: '#0284C7',         // Info Blue
  
  // Backgrounds
  white: '#FFFFFF',
  gray50: '#F8FAFC',
  gray100: '#F1F5F9',
  gray900: '#0F172A',
  
  // Text
  textPrimary: '#0F172A',
  textSecondary: '#64748B',
  textMuted: '#94A3B8'
}
```

---

## Bottom Tab Navigation Structure

### Tab Bar Design
- **Style:** Modern glassmorphism tab bar with smooth icon transitions
- **Position:** Bottom navigation with safe area considerations
- **Icons:** Custom healthcare and family-focused iconography

### Four Main Tabs

#### **Home Tab**
**Purpose:** Daily health overview and quick actions for the primary elderly person

**Interface Components:**
- **Today's Health Summary Card:** Current vital signs status with color-coded health indicators
- **Quick Actions Section:** "Record Vitals", "Take Medication", "Add Note" buttons
- **Recent Activity Feed:** Latest health entries and family member activity
- **Health Alerts:** Any concerning readings or missed medications prominently displayed
- **Weather & Prayer Times Widget:** Malaysian context for medication timing

#### **Family Tab**
**Purpose:** Comprehensive elderly profile and detailed health management

**Interface Structure:**

**Elderly Profile Header:**
- Avatar: Large profile photo of elderly person
- Personal Info: Name, age, relationship (Nenek, Atuk, etc.)
- Quick Status: Overall health status indicator with color coding

**Vital Signs Card (Glassmorphism):**
- Combined Vitals Display: BP, SpO2, Pulse, Respiratory Rate, Temperature in single card
- Color-Coded Status: Normal (green), Concerning (amber), Critical (red)
- Last Reading Timestamp: When and who recorded the data
- Tap to Expand: Individual vital sign detail views

**Medication Management Card:**
- Today's Medications: Current schedule with taken/pending status
- Recent Adherence: Weekly compliance overview
- Tap for History: Full medication history and patterns

**Appointments Card:**
- Next Appointment: Upcoming doctor visits with countdown
- Recent Visits: Past appointments and follow-up requirements
- Tap for Calendar: Full appointment management interface

**Notes & Care Card:**
- Latest Family Notes: Recent observations and care updates
- Care Level Indicator: Independent/Dependent/Bedridden status
- Tap for Details: Full notes history and care coordination

**Elderly Description Section:**
- Medical Conditions: Current diagnoses and health status
- Current Medications: Active prescriptions and dosages
- Care Requirements: Daily assistance needs and restrictions
- Emergency Contacts: Family and medical contact information

#### **Insights Tab**
**Purpose:** Health trends, analytics, and long-term health management

**Interface Components:**
- **Health Trends Charts:** Blood pressure, glucose, weight trends over time
- **Medication Compliance Analytics:** Adherence patterns and improvements
- **Family Engagement Metrics:** Who's most active in health management
- **Health Goals & Milestones:** Progress tracking and achievement celebrations
- **Doctor Report Generation:** Summarized health data for medical appointments
- **Health Education Content:** Malaysian elderly health tips and information

#### **Profile Tab**
**Purpose:** User account management and app settings (Grab/Foodpanda style)

**Interface Structure:**
- **User Profile Section:** Photo, name, role in family, contact information
- **Family Management:** Switch between families, invite members, role management
- **App Settings:** Notifications, language (English/Bahasa Malaysia), privacy
- **Health Preferences:** Units (mmHg, mmol/L), reminder timings, prayer time integration
- **Support & Help:** FAQ, contact support, user guides
- **About & Legal:** App version, terms of service, privacy policy

---

## Development Strategy

### Frontend-First Development Approach
**Philosophy:** Build the complete mobile interface with placeholder functionality, then design the database schema based on the frontend requirements.

**Benefits:**
- Visual validation of user flows before database commitment
- Rapid prototyping and user testing with realistic interfaces
- Database schema optimized for actual frontend data needs
- Faster iteration on UI/UX without backend dependencies

---

## Development Implementation Phases

### Phase 1A: Project Setup & Navigation Foundation
- Expo + React Native project initialization with TypeScript
- React Navigation 6 bottom tab navigator implementation
- SafeAreaProvider wrapper component for consistent safe area handling
- Mock data structure creation for all health and family information
- Basic authentication screens with placeholder functionality

### Phase 1B: Onboarding & Welcome Flow
- Splash screen with app branding and loading states
- 5-slide welcome sequence with swipeable navigation and illustrations
- Authentication interface with login/register toggle (non-functional backend)
- First-time user experience complete flow testing

### Phase 1C: Core Screen Structure & Navigation
- Home screen implementation with daily health overview
- Family screen layout with elderly profile and health cards
- Insights screen foundation with placeholder charts and analytics
- Profile screen implementation with settings and user management

### Phase 1D: Family Screen Detailed Implementation
- Elderly profile header with avatar and personal information
- Glassmorphism vital signs card with color-coded health status
- Medication management interface with adherence tracking
- Appointments system with calendar integration preparation
- Notes and care coordination features

### Phase 1E: Interactions & Polish
- Card tap interactions for detailed health data views
- Modal screens for individual vital sign management
- Smooth animations and modern app transitions
- Malaysian cultural elements integration throughout interface

---

## Mock Data Structure

### Elderly Person Mock Data
```json
{
  "elderlyProfile": {
    "name": "Hajah Aminah binti Abdullah",
    "age": 74,
    "relationship": "Nenek",
    "avatar": "placeholder_elderly_woman.jpg",
    "careLevel": "dependent",
    "conditions": ["Hypertension", "Type 2 Diabetes"],
    "currentMedications": ["Amlodipine 5mg", "Metformin 500mg"],
    "emergencyContact": "+60123456789"
  }
}
```

### Vital Signs Mock Data
```json
{
  "vitals": {
    "bloodPressure": {"systolic": 145, "diastolic": 90, "status": "concerning"},
    "spO2": {"value": 98, "status": "normal"},
    "pulse": {"value": 72, "status": "normal"},
    "respiratoryRate": {"value": 16, "status": "normal"},
    "temperature": {"value": 36.5, "status": "normal"},
    "lastRecorded": "2024-01-15T09:30:00Z",
    "recordedBy": "Ahmad (Anak)"
  }
}
```
---

## Technical Implementation Notes

### Tech Stack
- **React Native** (iOS + Android)
- **Supabase** (backend + database)
- **Hosted in Singapore** (good enough for Malaysia)

### Accessibility Considerations
- **High contrast options** for users with vision difficulties
- **Simple navigation patterns** for users with limited tech experience

### Performance Optimization
- **Efficient glassmorphism** implementation with fallbacks
- **Optimized illustrations** and image loading
- **Smooth animations** without performance impact
- **Memory management** for older Android devices

---

## Revenue Model

### Free Tier
- Basic tracking for 1 elderly person
- Up to 3 family members
- With mobile ads

### Premium (RM19.90/month)
- Up to 5 family members
- Detailed health reports
- Priority support
- **No ads**

---

## Go-to-Market Strategy

1. **Facebook/Instagram/TikTok ads** targeting adult children in KL (20-45 years old)
2. **Pharmacy partnerships** - demo at Guardian/Watsons with BP monitor bundles
3. **Word of mouth** - referral program for families

---

## Success Metrics (6 Months)

- 1,000 active elderly profiles
- 70% user retention after 1 month
- Average 3 family members per elderly person
- 15% conversion to premium

---

## Database Design Considerations (Post-Frontend)

### Tables to Design Based on Frontend Needs
- **users:** User profiles and authentication data
- **elderly_profiles:** Comprehensive elderly person information
- **vital_signs:** All health measurements with timestamps
- **medications:** Medication schedules and adherence tracking
- **appointments:** Medical appointments and care coordination
- **care_notes:** Family communication and care observations

### Malaysian Healthcare Data Requirements
- **Clinical thresholds:** Local medical standards for vital signs
- **Medication database:** Common Malaysian elderly prescriptions
- **Multi-tenant architecture:** Family-based data isolation and sharing