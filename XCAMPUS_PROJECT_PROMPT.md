# XCampus Interview Preparation Platform - Complete Project Prompt

## Project Overview
Create a comprehensive Next.js 14 interview preparation platform called "XCampus" that connects students and professionals through shared interview experiences, Q&A, and a reward system.

## Design Requirements

### Color Scheme
- **Primary Background**: Cosmic Latte (#FFF8E8)
- **Primary Accent**: Chocolate (#7B3F00)
- **Complete Color System**: 
  - Primary: #7B3F00 (Chocolate)
  - Secondary: #8B4513 (Saddle Brown)
  - Accent: #D2691E (Chocolate Orange)
  - Success: #22C55E
  - Warning: #F59E0B
  - Error: #EF4444
  - Neutral grays: #F8F9FA, #E9ECEF, #6C757D, #495057, #212529

### Typography & Spacing
- Font: Inter (primary), system fonts fallback
- Spacing: 4px base unit system
- Line height: 150% for body text, 120% for headings
- Max 3 font weights

### Responsive Design
- Mobile-first approach
- Breakpoints: 640px (sm), 768px (md), 1024px (lg), 1280px (xl)
- Consistent 8px spacing system

## Technical Stack
- **Framework**: Next.js 14 with App Router
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **Forms**: React Hook Form + Zod validation
- **Icons**: Lucide React
- **Theme**: next-themes for dark/light mode
- **State**: React hooks and context

## Core Features to Implement

### 1. Landing Page Components
Create a comprehensive landing page with these sections:

#### Hero Section
- Compelling headline about interview preparation
- Subtitle explaining the platform's value
- Primary CTA button "Get Started"
- Key statistics (users, experiences, success rate)
- Background with subtle gradients

#### How It Works (4 Steps)
1. **Sign Up** - Create your profile
2. **Share** - Add your interview experiences
3. **Learn** - Browse others' experiences and ask questions
4. **Earn** - Get points and redeem rewards

#### Features Grid
- **Real Experiences** - Authentic interview stories
- **Q&A Community** - Ask and answer questions
- **Company Insights** - Learn about different companies
- **Reward System** - Earn points for contributions
- **AI Assistant** - Get personalized help
- **Expert Network** - Connect with professionals

#### Benefits Section (Tabbed)
- **For Students**: Practice, learn, prepare, network
- **For Professionals**: Share knowledge, build reputation, help others

#### Testimonials Carousel
- 5+ testimonials with photos, names, roles, and ratings
- Auto-rotating carousel with manual controls

#### Rewards Visualization
- Visual flow showing: Contribute → Earn Points → Redeem Rewards
- Sample rewards: courses, books, mentorship sessions

#### AI Integration Highlight
- Prominent "Ask AI" chat interface
- Showcase AI-powered features

#### Alumni Success Scroll
- Right-to-left scrolling photos of successful alumni
- Company logos where they work

#### FAQ Section
- Expandable accordion with 8+ common questions
- Cover registration, points, rewards, privacy

#### Footer
- Company info, links, social media
- Newsletter signup
- Legal links

### 2. Authentication System

#### Registration (Multi-step)
- **Step 1**: Basic info (name, email, password)
- **Step 2**: Profile details (university, graduation year, field)
- **Step 3**: Profile picture upload and role selection
- Progress indicator throughout
- Form validation with error messages

#### Login Page
- Email/password form
- "Remember me" option
- Forgot password link
- Social login buttons (mock)

#### Protected Routes
- Redirect unauthenticated users to login
- Persistent sessions using localStorage
- User context throughout app

### 3. Core Application Pages

#### Dashboard
- Welcome message with user name
- Key statistics cards (experiences shared, questions asked, points earned)
- Quick action buttons
- Recent activity feed
- Profile completion progress
- Upcoming features/notifications

#### Experiences Page
- Grid/list view of interview experiences
- Advanced filtering:
  - Company (Google, Microsoft, Amazon, etc.)
  - Role (SDE, PM, Designer, etc.)
  - Difficulty (Easy, Medium, Hard)
  - Type (Technical, Behavioral, Case Study)
- Search functionality
- Detailed experience cards with:
  - Company logo and name
  - Role and difficulty
  - Experience summary
  - Author info and date
  - Upvote/downvote system

#### Questions Page
- Q&A interface similar to Stack Overflow
- Categories: Technical, Behavioral, Company-specific
- Question cards with:
  - Title and description
  - Tags and category
  - Author info and timestamp
  - Answer count and votes
- Ask new question form
- Search and filter functionality

#### Rewards Page
- Current point balance prominently displayed
- Available rewards grid:
  - Online courses (100-500 points)
  - Books and resources (50-200 points)
  - Mentorship sessions (300-1000 points)
  - Company swag (150-400 points)
- Point earning opportunities
- Transaction history
- Redemption process

### 4. UI Component Library
Create reusable components:
- Button (variants: primary, secondary, outline, ghost)
- Card (with header, content, footer)
- Input (text, email, password, search)
- Textarea
- Select dropdown
- Progress bar
- Badge/Tag
- Avatar
- Modal/Dialog
- Toast notifications
- Loading spinners
- Empty states

### 5. Navigation & Layout

#### Header/Navigation
- Logo and brand name
- Main navigation links
- User menu with avatar
- Notifications bell
- Theme toggle
- Mobile hamburger menu

#### Sidebar (Dashboard pages)
- Navigation links with icons
- User profile summary
- Point balance
- Quick actions

#### Breadcrumbs
- Show current page hierarchy
- Clickable navigation

### 6. Data Structure & Mock Data

#### User Profile
```typescript
interface User {
  id: string;
  name: string;
  email: string;
  avatar?: string;
  university: string;
  graduationYear: number;
  field: string;
  role: 'student' | 'professional';
  points: number;
  reputation: number;
  joinedDate: Date;
  experiencesShared: number;
  questionsAsked: number;
  questionsAnswered: number;
}
```

#### Interview Experience
```typescript
interface Experience {
  id: string;
  title: string;
  company: string;
  role: string;
  difficulty: 'Easy' | 'Medium' | 'Hard';
  type: 'Technical' | 'Behavioral' | 'Case Study';
  description: string;
  author: User;
  date: Date;
  upvotes: number;
  downvotes: number;
  tags: string[];
}
```

#### Question
```typescript
interface Question {
  id: string;
  title: string;
  description: string;
  category: string;
  tags: string[];
  author: User;
  date: Date;
  answers: Answer[];
  upvotes: number;
  views: number;
}
```

#### Reward
```typescript
interface Reward {
  id: string;
  title: string;
  description: string;
  pointsCost: number;
  category: string;
  image: string;
  available: boolean;
  estimatedDelivery: string;
}
```

### 7. Mock Data Requirements
Create realistic mock data:
- 10+ interview experiences from various companies
- 15+ questions across different categories
- 8+ rewards in different point ranges
- 5+ user profiles
- Sample transaction history
- Testimonials with realistic details

### 8. Advanced Features

#### Search & Filtering
- Global search across experiences and questions
- Advanced filters with multiple criteria
- Sort options (date, popularity, difficulty)
- Filter persistence in URL params

#### Point System
- Points for sharing experiences (50-100 points)
- Points for asking questions (10 points)
- Points for answering questions (20-50 points)
- Bonus points for highly rated content
- Daily login bonuses

#### User Interactions
- Upvote/downvote system
- Bookmarking/favorites
- Following other users
- Commenting system
- Sharing functionality

#### Responsive Design Details
- Mobile-optimized navigation
- Touch-friendly interactions
- Optimized layouts for different screen sizes
- Progressive enhancement

### 9. Performance & Accessibility

#### Performance
- Image optimization with Next.js Image component
- Lazy loading for lists and images
- Proper loading states
- Error boundaries

#### Accessibility
- ARIA labels and roles
- Keyboard navigation support
- Screen reader compatibility
- Color contrast compliance
- Focus management

### 10. Development Guidelines

#### Code Organization
- Feature-based folder structure
- Separate components, hooks, utils, types
- Consistent naming conventions
- TypeScript interfaces for all data structures

#### Styling Guidelines
- Tailwind utility classes
- Custom CSS variables for theme colors
- Consistent spacing and typography
- Hover and focus states for all interactive elements

#### Form Handling
- React Hook Form for all forms
- Zod schemas for validation
- Proper error handling and display
- Loading states during submission

## Implementation Priority
1. Set up Next.js project with TypeScript and Tailwind
2. Create UI component library
3. Build landing page
4. Implement authentication system
5. Create core application pages
6. Add advanced features and interactions
7. Optimize for performance and accessibility

## Success Criteria
- Fully responsive design that works on all devices
- Complete user flow from registration to reward redemption
- Professional, polished UI with smooth interactions
- Type-safe TypeScript implementation
- Accessible and performant application
- Realistic mock data that demonstrates all features

This prompt should result in a comprehensive, production-ready interview preparation platform that provides real value to users while showcasing modern web development best practices.