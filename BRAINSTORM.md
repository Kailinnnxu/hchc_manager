# HCHC Manager - Brainstorming & Planning Document

## Project Overview
A web application for organization/community management focused on professional networking events (conferences, meetups, workshops). The app enables organizations to manage members, create events, and helps users discover events, register, and track their professional network connections.

## Core Features

### 1. Event Management
- **Event Creation & Management**
  - Create events with details: title, description, date/time, location (physical/virtual), capacity
  - Event categories/tags (conference, meetup, workshop, etc.)
  - Event visibility settings (public, members-only, private)
  - Event status (draft, published, ongoing, completed, cancelled)
  - Rich text descriptions with images
  - Registration requirements/forms
  - Waitlist management

- **Event Discovery**
  - Browse/search events by date, category, location
  - Filter by event type, date range, location
  - Event recommendations based on user interests
  - Calendar view of events
  - Upcoming events dashboard

- **Event Application & Approval** (All events are closed-door)
  - Users apply to events (submit application)
  - Application status: pending, approved, rejected
  - Admin/manager review and approve/reject applications
  - Application form with required information
  - Capacity limits enforced during approval
  - Approved applicants receive confirmation
  - Check-in functionality for event organizers
  - Application withdrawal (before approval/rejection)
  - Waitlist for approved applicants if capacity reached

- **Attendance Tracking** (Admin/Manager Only)
  - Mark approved attendees as "attended" or "absent" after events
  - View attendance list for each event
  - Filter attendees by attendance status
  - Bulk mark attendance operations
  - Track who marked attendance and when
  - Export attendance reports
  - View attendance statistics per event

### 2. Contact & Network Management (Manager Only)
- **Contact Management** (Manager/Admin Access Required)
  - View all organization contacts (contact database)
  - Add contacts manually or import from events
  - Contact profiles: name, email, phone, company, title, bio, tags
  - Contact notes and interaction history
  - Tag/categorize contacts (colleague, client, mentor, etc.)
  - Contact search and filtering across all organization contacts
  - **Advanced Filtering & Screening**
    - Filter contacts by tags (single or multiple tags)
    - Search by keywords (name, email, company, title, bio)
    - Filter by company, job title, event attended
    - Combine multiple filters (tags + keywords + other criteria)
    - Save filter presets for common searches
  - **Contact Database Export**
    - Select specific fields to export (name, email, phone, company, title, tags, etc.)
    - Export filtered/screened contact lists
    - Export formats: CSV, Excel, JSON
    - Bulk export with custom field selection
    - Export includes only contacts matching current filters

- **Relationship Tracking** (Manager Access Required)
  - Track how contacts were met (which event, when)
  - Relationship strength/status indicators
  - Interaction history (meetings, emails, events attended together)
  - Notes and reminders about contacts

- **Network Visualization** (Manager Access Required)
  - Visual network graph showing all organization connections
  - Filter by event, company, relationship type
  - Identify mutual connections
  - Network statistics (total contacts, connections by event, etc.)
  - Organization-wide network analytics

### 3. Organization/Community Management
- **Member Management**
  - Member directory with profiles
  - Member roles and permissions (admin, organizer, member)
  - Member status (active, inactive, pending)
  - Member activity tracking
  - Bulk member operations

- **Organization Settings**
  - Organization profile (name, description, logo)
  - Organization settings and preferences
  - Email notifications configuration
  - Integration settings

### 4. User Features

#### Regular Users
- **User Profile** (View & Edit Own Profile)
  - View and edit personal profile
  - Quick onboarding collects essential info (4 minutes)
  - Extended profile editing available to add:
    - Additional contact information (phone, LinkedIn, personal website, GitHub) - WeChat already collected in onboarding
    - Extended professional details (company website, funding stage, previous companies, achievements)
    - Multiple education entries with full details
    - Structured interests & matchmaking (can_offer/looking_for with categories)
    - Bio & narrative (elevator pitch, full bio, publications, speaking experience)
    - Affiliations (professional organizations, alumni networks, accelerators, board positions)
    - Investment & funding details (for investors/founders)
    - Research & publications (for academics/researchers)
  - Profile picture
  - Privacy settings
  - Profile completeness indicator
  - View own event attendance history

- **Event List** (View Only)
  - Browse and search events
  - View event details
  - Apply for events (submit application)
  - View application status (pending, approved, rejected)
  - View approved events (events they've been approved for)

#### Managers/Admins
- **Manager Dashboard**
  - Upcoming approved events
  - Pending event applications to review
  - Organization-wide contact overview
  - Network growth metrics
  - Activity feed
  - Organization statistics

- **Event Application Management** (Admin/Manager Access)
  - Review pending event applications
  - Approve or reject applications
  - View all applications for an event
  - Filter applications by status
  - Bulk approve/reject operations
  - View application details and user profiles

- **Attendance Tracking** (Admin/Manager Access)
  - Mark attendees as "attended" or "absent" for events
  - Able to add 'insider notes'
  - View attendance list for each event
  - Filter attendees by attendance status
  - Bulk mark attendance operations
  - Export attendance reports

- **User Event History** (Admin/Manager Access)
  - View complete event history for any user/audience member
  - See all past events: application status (pending/approved/rejected)
  - See attendance status (attended/absent) for each past event
  - Filter by event status, date range, attendance status
  - View user's event participation statistics

- **Full Access**
  - All regular user features
  - Access to contact management (all organization contacts)
  - Network visualization dashboard
  - Organization analytics

### 5. Authentication & Authorization
- **Authentication**
  - Email/password registration and login
  - Password reset functionality
  - Email verification
  - Session management

- **Authorization**
  - Role-based access control (RBAC)
  - Organization-level permissions
  - **Regular Users**: Can only view their own profile and event list
  - **Managers**: Can view all contacts, network visualization, and organization dashboards
  - Event-level permissions (organizer, attendee, viewer)

### 6. User Onboarding & Profile Enrichment

- **Quick Onboarding (Target: 4 minutes)**
  - Streamlined initial onboarding to get users started quickly
  - Collects only essential information needed to begin using the platform
  - Detailed profile information can be added later in profile editing
  - Focus on getting users to their first event application quickly

- **LLM-Enhanced Data Processing**
  - **Structured Data Extraction & Normalization**
    - Normalize job titles and roles to standard categories
    - Extract and standardize company information
    - Parse and structure education data
    - Extract key information from free-text bios
  - **Intelligent Tagging & Categorization**
    - Auto-generate expertise tags from bio, interests, and experience
    - Categorize professional stage and network value
    - Generate matchmaking tags (mentor, investor, co-founder-seeker)
    - Identify Ivy League status, C-level positions, domain expertise
  - **Relationship & Network Mapping**
    - **Mutual connections potential**: Analyze company, school, field overlaps to identify potential connections
    - **Complementary profiles**: Match "can_offer" with "looking_for" across users to facilitate networking
    - **Influence indicators**: Identify thought leaders, serial entrepreneurs, notable investors based on profile analysis
  - **Data Enrichment from External Sources**
    - **LinkedIn profile parsing**: If LinkedIn URL provided, extract additional context and enrich profile data
    - **Company intelligence**: Enrich company info (size, funding stage, industry) from external data sources
    - **Education verification**: Cross-reference school names, verify degree programs for accuracy
    - **Professional validation**: Flag inconsistencies (e.g., claimed C-level at unknown company) for admin review
  - **Smart Application Review Assistance**
    - **Summarize applicant profile**: Generate 2-3 sentence summary highlighting key value and unique attributes
    - **Relevance scoring**: Score how well applicant matches event theme/audience
    - **Recommendation**: Suggest approve/reject with reasoning based on event criteria
    - **Highlight unique value**: Identify what makes this applicant special (Ivy League, startup founder, etc.)
  - **Searchable Knowledge Extraction**
    - **Skills inventory**: Parse "can_offer" into structured skills database for searchable metadata
    - **Interest mapping**: Create interest taxonomy from "professional_interests" for better categorization
    - **Geographic clustering**: Use city/timezone for regional network analysis and local connections
    - **Industry classification**: Auto-categorize into healthcare sub-domains (pharma, medtech, digital health, etc.)

- **Quick Onboarding Structure (4 minutes)**
  - **Step 1: Basic Info** (~1 min)
    - Name (first, last)
    - Email (already collected during registration)
    - WeChat (essential for communication)
    - Linkedin
    - Primary City, Country 
    - Secondary City, Country
  - **Step 2: Professional** (~1.5 min)
    - Current role/title
    - Current company
    - Professional stage (student, early-career, mid-career, senior, executive, founder, investor, academic)
    - Years of experience
  - **Step 3: Education** (~1 min)
    - Highest degree
    - School name
    - Major/field of study
    - Graduation year (optional)
  - **Step 4: Interests & Goals** (~30 sec)
    - Professional interests (quick tags)
    - What they can offer (brief)
    - What they're looking for (brief)
    - Affiliations (professional organizations, alumni networks, accelerators, board positions, advisory roles)
  - **Step 5: Other Information**
    - Where did you hear about us (XHS, Wechat GZH, word of mouth, related group chats)
  - **Step 6: Consent** (~30 sec)
    - Essential privacy and consent settings
    - Data enrichment consent

- **Extended Profile (Available in Profile Settings)**
  - Users can add detailed information after onboarding:
    - Additional contact information (phone, personal website, GitHub) 
    - Detailed professional info (company website, funding stage, department, team size, previous companies, current projects, achievements)
    - Extended education (multiple degrees, minors, honors, extracurriculars, thesis topics)
    - Detailed interests & matchmaking (structured can_offer/looking_for with categories and availability)
    - Bio & narrative (elevator pitch, full bio, publications, speaking experience, media mentions)
    - Investment & funding details (for investors/founders)
    - Research & publications (for academics/researchers)
    - Additional consent preferences

- **Quick Onboarding Data Structure (Minimum Required)**
  ```json
  {
    "personal_info": {
      "first_name": "string",
      "last_name": "string",
      "primary_city": "string?",
      "primary_country": "string?",
      "secondary_city": "string?",
      "secondary_country": "string?"
    },
    "contact": {
      "wechat": "string", // Essential for communication
      "linkedin": "string?" // LinkedIn profile URL
    },
    "professional": {
      "stage": "enum", // student, early-career, mid-career, senior, executive, founder, investor, academic
      "current_company": "string?",
      "role_title": "string?",
      "years_total_experience": "number?"
    },
    "education": {
      "degree": "string", // BS, BA, MS, MBA, PhD, MD, etc.
      "school": "string",
      "major": "string",
      "grad_year": "number?"
    },
    "interests": {
      "professional_interests": ["string"], // Quick tags
      "can_offer": "string?", // Brief text
      "looking_for": "string?", // Brief text
      "affiliations": ["string"]? // Professional organizations, alumni networks, accelerators, board positions, advisory roles
    },
    "onboarding_metadata": {
      "where_did_you_hear_about_us": "enum?" // XHS, Wechat GZH, word of mouth, related group chats
    },
    "consent": {
      "share_with_presenter": "boolean",
      "public_directory": "boolean",
      "notifications": "boolean",
      "data_enrichment": "boolean"
    }
  }
  ```

- **Extended Profile Data Structure (Available in Profile Settings)**
  ```json
  {
    "personal_info": {
      "preferred_name": "string?",
      "pronunciation": "string?",
      "state_province": "string?",
      "country": "string?",
    },
    "contact": {
      "wechat": "string?",
      "phone": "string?",
      "linkedin": "string?",
      "personal_website": "string?",
      "github": "string?",
      "preferred_contact_method": "enum?"
    },
    "professional": {
      "company_website": "string?",
      "company_funding_stage": "enum?",
      "role_category": "enum?",
      "department": "string?",
      "years_in_current_role": "number?",
      "reports_to": "string?",
      "team_size": "number?",
      "fields": ["string"],
      "years_experience_per_field": {"field_name": "number"},
      "previous_companies": [{"company": "string", "role": "string", "start_date": "date?", "end_date": "date?"}],
      "current_projects": ["string"]?,
      "notable_achievements": ["string"]?
    },
    "education": [{
      "degree": "string",
      "degree_level": "enum?",
      "school": "string",
      "school_type": "enum?",
      "major": ["string"],
      "minor": ["string"]?,
      "grad_year": "number?",
      "gpa": "number?",
      "honors": ["string"]?,
      "extracurriculars": ["string"]?,
      "study_abroad": "boolean?",
      "thesis_dissertation_topic": "string?"
    }],
    "interests": {
      "can_offer": [{"category": "enum", "description": "string", "availability": "enum?"}],
      "looking_for": [{"category": "enum", "description": "string", "urgency": "enum?"}],
      "event_types_preferred": ["enum"]?,
      "networking_goals": ["string"]?
    },
    "bio": {
      "elevator_pitch": "string?",
    },
    "affiliations": {
      "professional_organizations": ["string"]?,
      "alumni_networks": ["string"]?,
      "accelerators_programs": ["string"]?,
      "board_positions": ["string"]?,
      "advisory_roles": ["string"]?,
      "investor_network": "boolean?",
      "mentor_programs": ["string"]?
    },
    "investment": {
      "is_investor": "boolean?",
      "investment_focus": ["string"]?,
      "investment_stage": ["enum"]?,
      "typical_check_size": "enum?",
      "portfolio_companies": ["string"]?,
      "seeking_funding": "boolean?",
      "funding_stage_seeking": "enum?",
      "funding_amount_seeking": "enum?"
    },
    "research": {
      "research_interests": ["string"]?,
      "current_research": "string?",
      "lab_institution": "string?",
      "grants_received": ["string"]?,
      "patents": [{"title": "string", "number": "string?", "year": "number?"}]
    },
    "consent": {
      "share_with_presenter": "boolean",
      "notifications": "boolean",
    },
    "verification": {
      "email_verified": "boolean",
    }
  }
  ```

## Database Schema

### Core Tables

#### Users
- `id` (UUID, Primary Key)
- `email` (String, Unique, Indexed)
- `password_hash` (String)
- `first_name` (String)
- `last_name` (String)
- `preferred_name` (String, Nullable)
- `pronunciation` (String, Nullable)
- `profile_picture_url` (String, Nullable)
- `email_verified` (Boolean, Default: false)
- `email_verification_token` (String, Nullable)
- `password_reset_token` (String, Nullable)
- `password_reset_expires` (DateTime, Nullable)
- `created_at` (DateTime)
- `updated_at` (DateTime)
- `last_login_at` (DateTime, Nullable)
- `onboarding_completed` (Boolean, Default: false)
- `onboarding_step` (Integer, Default: 1)

#### User_Profiles (Extended Profile Data)
- `id` (UUID, Primary Key)
- `user_id` (UUID, Foreign Key -> Users, Unique)
- `personal_info` (JSONB, Nullable) - {primary_city, primary_country, secondary_city, secondary_country, state_province, timezone, languages, date_of_birth} - primary_city/country collected in onboarding
- `contact_info` (JSONB, Nullable) - {wechat, phone, linkedin, twitter, personal_website, github, preferred_contact_method} - wechat and linkedin collected in onboarding
- `professional_info` (JSONB, Nullable) - {stage, current_company, company_website, company_size, company_funding_stage, role_title, role_category, department, years_in_current_role, years_total_experience, reports_to, team_size, fields, years_experience_per_field, previous_companies, current_projects, notable_achievements}
- `education` (JSONB, Nullable) - Array of {degree, degree_level, school, school_type, major, minor, grad_year, gpa, honors, extracurriculars, study_abroad, thesis_dissertation_topic}
- `interests` (JSONB, Nullable) - {professional_interests, can_offer, looking_for, affiliations, event_types_preferred, networking_goals} - basic affiliations collected in onboarding
- `bio` (JSONB, Nullable) - {short, long, elevator_pitch, key_achievements, publications, speaking_experience, media_mentions}
- `affiliations` (JSONB, Nullable) - {professional_organizations, alumni_networks, accelerators_programs, board_positions, advisory_roles, investor_network, mentor_programs} - detailed affiliations (extended profile)
- `onboarding_metadata` (JSONB, Nullable) - {where_did_you_hear_about_us} - collected during onboarding
- `investment` (JSONB, Nullable) - {is_investor, investment_focus, investment_stage, typical_check_size, portfolio_companies, seeking_funding, funding_stage_seeking, funding_amount_seeking}
- `research` (JSONB, Nullable) - {research_interests, current_research, lab_institution, grants_received, patents}
- `consent` (JSONB, Nullable) - {share_with_presenter, public_directory, notifications, data_enrichment, profile_completeness_public, contact_sharing, linkedin_import, marketing_communications}
- `verification` (JSONB, Nullable) - {email_verified}
- `created_at` (DateTime)
- `updated_at` (DateTime)

#### User_LLM_Enrichment (LLM-Generated Insights)
- `id` (UUID, Primary Key)
- `user_id` (UUID, Foreign Key -> Users, Unique)
- `normalized_role` (String, Nullable)
- `role_category` (Enum, Nullable) - C-Level, VP/Director, Manager, IC, Founder, Investor, Academic
- `seniority_level` (String, Nullable)
- `company_size` (String, Nullable)
- `funding_stage` (String, Nullable)
- `ivy_league` (Boolean, Default: false)
- `expertise_tags` (Array/JSON, Nullable) - LLM-extracted tags
- `network_value_score` (Integer, Nullable) - 1-100
- `matchmaking_tags` (Array/JSON, Nullable) - mentor, investor, co-founder-seeker, etc.
- `enrichment_metadata` (JSONB, Nullable) - {llm_model_version, confidence_scores, extraction_timestamp}
- `last_enriched_at` (DateTime, Nullable)
- `created_at` (DateTime)
- `updated_at` (DateTime)

#### Organizations
- `id` (UUID, Primary Key)
- `name` (String)
- `slug` (String, Unique, Indexed)
- `description` (Text, Nullable)
- `logo_url` (String, Nullable)
- `website` (String, Nullable)
- `settings` (JSON, Nullable) - flexible settings storage
- `created_at` (DateTime)
- `updated_at` (DateTime)

#### Organization_Members
- `id` (UUID, Primary Key)
- `organization_id` (UUID, Foreign Key -> Organizations)
- `user_id` (UUID, Foreign Key -> Users)
- `role` (Enum: 'admin', 'manager', 'organizer', 'member')
  - 'admin': Full organization control
  - 'manager': Can view all contacts, network visualization, dashboards
  - 'organizer': Can create/manage events
  - 'member': Regular user (profile + event list only)
- `status` (Enum: 'active', 'inactive', 'pending')
- `joined_at` (DateTime)
- `created_at` (DateTime)
- `updated_at` (DateTime)
- Unique constraint: (organization_id, user_id)

#### Events
- `id` (UUID, Primary Key)
- `organization_id` (UUID, Foreign Key -> Organizations)
- `created_by` (UUID, Foreign Key -> Users)
- `title` (String)
- `slug` (String, Unique, Indexed)
- `description` (Text)
- `event_type` (Enum: 'conference', 'meetup', 'workshop', 'other')
- `start_date` (DateTime)
- `end_date` (DateTime)
- `location_type` (Enum: 'physical', 'virtual', 'hybrid')
- `location_name` (String, Nullable)
- `location_address` (Text, Nullable)
- `virtual_link` (String, Nullable)
- `capacity` (Integer, Nullable)
- `status` (Enum: 'draft', 'published', 'ongoing', 'completed', 'cancelled')
- `visibility` (Enum: 'public', 'members-only', 'private')
- `application_required` (Boolean, Default: true) - all events require application
- `application_deadline` (DateTime, Nullable) - deadline for submitting applications
- `requires_approval` (Boolean, Default: true) - all events require admin approval
- `tags` (Array/JSON, Nullable)
- `image_url` (String, Nullable)
- `created_at` (DateTime)
- `updated_at` (DateTime)

#### Event_Applications
- `id` (UUID, Primary Key)
- `event_id` (UUID, Foreign Key -> Events)
- `user_id` (UUID, Foreign Key -> Users)
- `status` (Enum: 'pending', 'approved', 'rejected', 'withdrawn', 'checked_in', 'cancelled', 'waitlisted')
- `application_data` (JSON, Nullable) - custom application form responses
- `applied_at` (DateTime)
- `reviewed_by` (UUID, Foreign Key -> Users, Nullable) - admin who reviewed the application
- `reviewed_at` (DateTime, Nullable)
- `rejection_reason` (Text, Nullable) - reason if rejected
- `checked_in_at` (DateTime, Nullable)
- `attendance_status` (Enum: 'attended', 'absent', NULL) - NULL if event hasn't occurred or not yet marked
- `attendance_marked_by` (UUID, Foreign Key -> Users, Nullable) - admin who marked attendance
- `attendance_marked_at` (DateTime, Nullable)
- `cancelled_at` (DateTime, Nullable)
- `created_at` (DateTime)
- `updated_at` (DateTime)
- Unique constraint: (event_id, user_id) where status NOT IN ('withdrawn', 'cancelled')

#### Contacts
- `id` (UUID, Primary Key)
- `organization_id` (UUID, Foreign Key -> Organizations) - organization that owns this contact
- `created_by` (UUID, Foreign Key -> Users) - manager who created this contact
- `contact_user_id` (UUID, Foreign Key -> Users, Nullable) - if contact is a registered user in the system
- `first_name` (String)
- `last_name` (String)
- `email` (String, Nullable)
- `phone` (String, Nullable)
- `company` (String, Nullable)
- `job_title` (String, Nullable)
- `bio` (Text, Nullable)
- `profile_picture_url` (String, Nullable)
- `tags` (Array/JSON, Nullable)
- `notes` (Text, Nullable)
- `created_at` (DateTime)
- `updated_at` (DateTime)
- Index on organization_id

#### Contact_Events
- `id` (UUID, Primary Key)
- `contact_id` (UUID, Foreign Key -> Contacts)
- `event_id` (UUID, Foreign Key -> Events)
- `met_at` (DateTime) - when they met at this event
- `notes` (Text, Nullable)
- `created_at` (DateTime)
- Unique constraint: (contact_id, event_id)

#### Contact_Interactions
- `id` (UUID, Primary Key)
- `contact_id` (UUID, Foreign Key -> Contacts)
- `interaction_type` (Enum: 'meeting', 'email', 'call', 'event', 'other')
- `title` (String)
- `description` (Text, Nullable)
- `interaction_date` (DateTime)
- `created_at` (DateTime)
- `updated_at` (DateTime)
- Index on contact_id

#### Relationships
- `id` (UUID, Primary Key)
- `organization_id` (UUID, Foreign Key -> Organizations) - organization context
- `contact_id` (UUID, Foreign Key -> Contacts)
- `relationship_type` (Enum: 'colleague', 'client', 'mentor', 'mentee', 'friend', 'other')
- `strength` (Integer, 1-5, Nullable) - relationship strength rating
- `notes` (Text, Nullable)
- `created_at` (DateTime)
- `updated_at` (DateTime)
- Index on organization_id, contact_id

## Tech Stack Recommendations

### Frontend
- **Framework**: React (with TypeScript) or Next.js for SSR/SSG
- **UI Library**: Tailwind CSS + shadcn/ui or Material-UI
- **State Management**: React Query (TanStack Query) for server state, Zustand/Redux for client state
- **Forms**: React Hook Form + Zod for validation
- **Charts/Visualization**: Recharts or D3.js for network graphs
- **Date Handling**: date-fns or dayjs
- **HTTP Client**: Axios or fetch with React Query

### Backend
- **Framework**: Node.js with Express or Fastify, OR Python with FastAPI/Django
- **Language**: TypeScript (Node.js) or Python
- **Database**: PostgreSQL (recommended) or MySQL
- **ORM**: Prisma (TypeScript) or SQLAlchemy (Python)
- **Authentication**: JWT tokens with refresh tokens, bcrypt for password hashing
- **Email**: SendGrid, AWS SES, or Resend for transactional emails
- **File Storage**: AWS S3, Cloudinary, or local storage for development
- **LLM Integration**: OpenAI API, Anthropic Claude, or self-hosted models
  - For profile enrichment, data extraction, and intelligent tagging
  - Batch processing for existing users
  - Real-time enrichment on profile updates

### Infrastructure
- **Hosting**: Vercel/Netlify (frontend), Railway/Render/Fly.io (backend)
- **Database Hosting**: Supabase, Railway, or AWS RDS
- **CI/CD**: GitHub Actions
- **Monitoring**: Sentry for error tracking

## Architecture Overview

### High-Level Architecture
```
┌─────────────────┐
│   Frontend      │
│   (React/Next)  │
└────────┬────────┘
         │ HTTP/REST API
┌────────▼────────┐
│   Backend API   │
│  (Express/Fast) │
└────────┬────────┘
         │
┌────────▼────────┐
│   PostgreSQL    │
│    Database     │
└─────────────────┘
```

### Key API Endpoints (RESTful)

#### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `POST /api/auth/logout` - User logout
- `POST /api/auth/refresh` - Refresh access token
- `POST /api/auth/forgot-password` - Request password reset
- `POST /api/auth/reset-password` - Reset password
- `GET /api/auth/verify-email` - Verify email address

#### Organizations
- `GET /api/organizations` - List organizations (user's orgs)
- `GET /api/organizations/:id` - Get organization details
- `POST /api/organizations` - Create organization
- `PUT /api/organizations/:id` - Update organization
- `DELETE /api/organizations/:id` - Delete organization
- `GET /api/organizations/:id/members` - List organization members
- `POST /api/organizations/:id/members` - Add member
- `PUT /api/organizations/:id/members/:userId` - Update member role
- `DELETE /api/organizations/:id/members/:userId` - Remove member

#### Events
- `GET /api/events` - List events (with filters)
- `GET /api/events/:id` - Get event details
- `POST /api/events` - Create event (admin/organizer)
- `PUT /api/events/:id` - Update event (admin/organizer)
- `DELETE /api/events/:id` - Delete event (admin/organizer)
- `POST /api/events/:id/apply` - Apply for event (submit application)
- `DELETE /api/events/:id/apply` - Withdraw application (if pending)
- `GET /api/events/:id/application` - Get user's application status for event
- `POST /api/events/:id/check-in` - Check in attendee (admin/organizer)
- `GET /api/events/:id/applications` - List all applications for event (admin/organizer)
- `PUT /api/events/:id/applications/:applicationId/approve` - Approve application (admin/organizer)
- `PUT /api/events/:id/applications/:applicationId/reject` - Reject application (admin/organizer)
- `PUT /api/events/:id/applications/:applicationId` - Update application status (admin/organizer)
- `PUT /api/events/:id/applications/:applicationId/attendance` - Mark attendance (attended/absent) (admin/organizer)
- `GET /api/events/:id/attendance` - Get attendance list for event (admin/organizer)
- `PUT /api/events/:id/attendance/bulk` - Bulk mark attendance (admin/organizer)

#### Contacts (Manager/Admin Only)
- `GET /api/contacts` - List all organization contacts with filtering (manager/admin only)
  - Query params: tags, keywords, company, job_title, event_id, etc.
  - Supports pagination and sorting
- `GET /api/contacts/:id` - Get contact details (manager/admin only)
- `POST /api/contacts` - Create contact (manager/admin only)
- `PUT /api/contacts/:id` - Update contact (manager/admin only)
- `DELETE /api/contacts/:id` - Delete contact (manager/admin only)
- `GET /api/contacts/:id/interactions` - Get contact interactions (manager/admin only)
- `POST /api/contacts/:id/interactions` - Add interaction (manager/admin only)
- `GET /api/contacts/:id/events` - Get events where contact was met (manager/admin only)
- `GET /api/contacts/export` - Export contacts with field selection (manager/admin only)
  - Query params: fields (comma-separated), filters (tags, keywords, etc.), format (csv, excel, json)
  - Returns filtered contact data with only selected fields
- `GET /api/contacts/filters/presets` - Get saved filter presets (manager/admin only)
- `POST /api/contacts/filters/presets` - Save filter preset (manager/admin only)

#### Network (Manager Only)
- `GET /api/network/graph` - Get network graph data (manager only)
- `GET /api/network/stats` - Get network statistics (manager only)
- `GET /api/network/mutual-connections/:contactId` - Get mutual connections (manager only)

#### Users
- `GET /api/users/me` - Get current user profile
- `PUT /api/users/me` - Update current user profile
- `GET /api/users/:id` - Get user profile (public)
- `GET /api/users/:id/event-history` - Get user's complete event history (admin/manager only)
  - Returns all past events with application status and attendance status
  - Filterable by date range, event status, attendance status

#### Onboarding (Quick - 6 steps, ~4 minutes)
- `GET /api/onboarding/status` - Get current onboarding status and step
- `POST /api/onboarding/step/:stepNumber` - Submit onboarding step data (steps 1-6)
  - Step 1: Basic info (name, WeChat, LinkedIn, primary city/country, secondary city/country)
  - Step 2: Professional (role, company, stage, experience)
  - Step 3: Education (degree, school, major, grad year)
  - Step 4: Interests & Goals (professional interests, can_offer, looking_for, affiliations)
  - Step 5: Other Information (where did you hear about us)
  - Step 6: Consent (privacy settings, data enrichment)
- `PUT /api/onboarding/step/:stepNumber` - Update onboarding step data
- `GET /api/onboarding/profile` - Get onboarding profile data
- `POST /api/onboarding/complete` - Mark onboarding as complete (triggers LLM enrichment automatically)

#### Profile Editing (Extended Profile Data)
- `GET /api/users/me/profile` - Get full extended profile data
- `PUT /api/users/me/profile` - Update extended profile sections
  - Personal info (preferred name, timezone, languages, etc.)
  - Contact info (phone, WeChat, LinkedIn, personal website, GitHub)
  - Extended professional (company details, previous companies, achievements)
  - Multiple education entries
  - Detailed interests & matchmaking
  - Bio & narrative
  - Affiliations
  - Investment & funding
  - Research & publications
- `GET /api/users/me/profile/completeness` - Get profile completeness score

#### LLM Enrichment (Admin/System)
- `POST /api/users/:id/enrich` - Trigger LLM enrichment for specific user (admin/system)
- `GET /api/users/:id/enrichment` - Get LLM enrichment data for user (admin/manager)
- `PUT /api/users/:id/enrichment` - Update LLM enrichment data (admin/system)
- `POST /api/enrichment/batch` - Batch enrich multiple users (admin/system)

## User Flows

### 1. User Registration & Quick Onboarding (Target: 4 minutes)
1. User visits app → Register page
2. Enter email, password → Submit
3. Email verification sent
4. User verifies email → Login
5. Redirected to quick onboarding flow
6. **Step 1: Basic Info** (~1 min)
   - First name, last name
   - WeChat (essential for communication)
   - LinkedIn
   - Primary city, country
   - Secondary city, country
7. **Step 2: Professional** (~1.5 min)
   - Current role/title
   - Current company
   - Professional stage (dropdown)
   - Years of experience
8. **Step 3: Education** (~1 min)
   - Highest degree
   - School name
   - Major/field
   - Graduation year (optional)
9. **Step 4: Interests & Goals** (~30 sec)
   - Professional interests (quick tag selection)
   - What can you offer? (brief text)
   - What are you looking for? (brief text)
   - Affiliations (professional organizations, alumni networks, accelerators, board positions, advisory roles)
10. **Step 5: Other Information**
    - Where did you hear about us (XHS, Wechat GZH, word of mouth, related group chats)
11. **Step 6: Consent** (~30 sec)
    - Essential privacy settings
    - Data enrichment consent
12. Onboarding complete → LLM enrichment triggered automatically
12. Dashboard shown with profile completion indicator
13. User can start browsing events immediately
14. Profile editing available to add detailed information later

### 2. Event Creation Flow
1. Admin/Organizer navigates to "Create Event"
2. Fill event form (title, description, date, location, capacity)
3. Set visibility settings (all events are closed-door, require approval)
4. Set application deadline (optional)
5. Publish event
6. Event appears in event listings (users can apply)

### 3. Event Discovery & Application
1. User browses events page
2. Filters/search events
3. Clicks event → View details
4. Click "Apply" → Fill application form
5. Submit application → Status: "Pending"
6. Receives confirmation email (application submitted)
7. Application appears in "My Applications" with pending status
8. Admin reviews application
9. Admin approves/rejects → User receives notification
10. If approved: Event appears in "My Approved Events"
11. If rejected: User can see rejection reason (if provided)

### 3b. Admin Application Review Flow
1. Admin navigates to event management
2. Views "Pending Applications" for an event
3. Clicks on application → Reviews application details and user profile
4. Approves or rejects application
5. Optionally adds rejection reason
6. System sends notification to applicant
7. If approved and capacity reached: User moved to waitlist

### 3c. Admin Attendance Tracking Flow
1. Admin navigates to completed or ongoing event
2. Views list of approved attendees
3. For each attendee, marks as "Attended" or "Absent"
4. Can bulk mark multiple attendees at once
5. Attendance status is saved and tracked
6. Can view attendance summary (total attended, total absent)
7. Can export attendance report

### 3d. Admin User Event History Flow
1. Admin navigates to user management or member directory
2. Clicks on a user/audience member
3. Views "Event History" tab
4. Sees complete list of all past events for that user:
   - Event name and date
   - Application status (pending/approved/rejected)
   - Attendance status (attended/absent/not marked)
   - Date applied, date reviewed, date attended (if applicable)
5. Can filter by:
   - Date range
   - Event status (completed, cancelled, etc.)
   - Application status
   - Attendance status
6. Can see user's event participation statistics:
   - Total events applied to
   - Total events approved
   - Total events attended
   - Total events absent
   - Attendance rate

### 4. Regular User Flow
1. User logs in
2. Views their profile (can edit)
3. Browses event list
4. Views event details
5. Applies for events
6. Views application status and approved events

### 4b. Profile Editing Flow
1. User navigates to "Edit Profile" from profile page
2. Sees profile completeness indicator
3. Can edit any section:
   - Personal information (extended details)
   - Contact information (WeChat - can update, phone, LinkedIn, etc.)
   - Extended professional details (previous companies, achievements, projects)
   - Multiple education entries with full details
   - Detailed interests & matchmaking (structured can_offer/looking_for)
   - Bio & narrative (elevator pitch, full bio, publications)
   - Affiliations (organizations, alumni networks, accelerators)
   - Investment & funding (if applicable)
   - Research & publications (if applicable)
4. Saves changes → Profile updated
5. LLM enrichment re-triggered automatically if enabled
6. Profile completeness score updated

### 5. Manager Contact Management Flow
1. Manager logs in
2. Navigates to "Contacts" page (visible only to managers/admins)
3. Views all organization contacts (contact database)
4. Can add new contacts manually or import from events
5. Link contact to event (when/where met)
6. Add notes, tags, relationship type
7. Contact saved to organization network

### 5b. Admin Contact Database Screening & Export Flow
1. Admin navigates to "Contacts" page
2. Views contact database with all organization contacts
3. Applies filters to screen contacts:
   - Filter by tags (select one or multiple tags)
   - Search by keywords (name, email, company, title, bio)
   - Filter by company, job title, event attended
   - Combine multiple filters
4. Views filtered contact list
5. Selects specific fields to include in export:
   - Name, email, phone, company, title, tags, bio, etc.
   - Can select/deselect individual fields
6. Chooses export format (CSV, Excel, JSON)
7. Downloads filtered contact list with selected fields only
8. Optionally saves filter preset for future use

### 6. Manager Network Visualization Flow
1. Manager navigates to "Network" page (visible only to managers)
2. View organization-wide network graph
3. Filter by event, company, relationship type
4. Click node → View contact details
5. See mutual connections
6. View network statistics and analytics

### 7. LLM Enrichment Processing Flow
1. User completes onboarding (or updates profile)
2. System triggers LLM enrichment process (automatic or manual)
3. LLM processes user profile data:
   - Normalizes job titles and roles
   - Extracts and structures company information
   - Parses education data
   - Generates expertise tags from bio and interests
   - Scores network value
   - Identifies matchmaking potential
   - Extracts key achievements
4. Enrichment data stored in User_LLM_Enrichment table
5. Admin can view enriched data alongside raw profile
6. Enrichment used for:
   - Smart application review summaries
   - Contact filtering and search
   - Network visualization
   - Matchmaking recommendations
7. Periodic re-enrichment as LLM models improve

## Security Considerations

- Password hashing with bcrypt (salt rounds: 10-12)
- JWT tokens with expiration (access: 15min, refresh: 7 days)
- HTTPS only in production
- Input validation and sanitization
- SQL injection prevention (use ORM/parameterized queries)
- CORS configuration
- Rate limiting on authentication endpoints
- Email verification before account activation
- Role-based access control (RBAC)
- Organization data isolation

## Future Enhancements (Phase 2+)

- Social login (Google, LinkedIn)
- Event calendar integration (Google Calendar, iCal)
- Advanced email notifications and reminders (application status changes, event reminders)
- Contact import (CSV, vCard) - export is in Phase 1/2
- Advanced analytics and reporting
- Mobile app (React Native)
- Real-time notifications (WebSockets)
- Event QR code check-in
- Event feedback and ratings
- Contact recommendations
- Integration with CRM systems
- API for third-party integrations

## Development Phases

### Phase 1: MVP (Minimum Viable Product)
- User authentication (email/password)
- Quick onboarding system (6 steps, ~4 minutes)
- Extended profile editing (users can add detailed information after onboarding)
- Basic organization management
- Role-based access control (regular users vs managers/admins)
- Event creation and listing (all users can view, managers/organizers can create)
- Event application system (all users can apply, all events require approval)
- Application review and approval workflow (admins/managers)
- Attendance tracking (mark attended/absent for events) (admins/managers)
- User event history viewing (view complete history: application status + attendance for past events) (admins/managers)
- User profile view/edit (regular users)
- Contact management (managers only)
- Contact database viewing (managers/admins only)
- Basic contact filtering and search (managers/admins only)
- Contact export with field selection (managers/admins only)
- Network visualization (managers only)
- Manager dashboard with pending applications
- Basic LLM enrichment (role normalization, basic tagging)

### Phase 2: Core Features
- Network visualization
- Relationship tracking
- Contact interactions
- Event check-in
- Advanced contact filtering (tags, keywords, multiple criteria combinations)
- Contact filter presets (save and reuse filters)
- Enhanced contact export (multiple formats, advanced field selection)
- Email notifications (application status updates, event reminders)
- Application bulk operations (bulk approve/reject)
- Attendance bulk operations (bulk mark attendance)
- Attendance reports and exports
- User participation analytics and statistics
- **Advanced LLM Enrichment**
  - Intelligent tagging and categorization
  - Relationship mapping and matchmaking
  - Batch LLM enrichment for existing users
  - Profile completeness scoring and recommendations
- **LLM-Assisted Application Review**
  - Summarize applicant profile: Generate 2-3 sentence summary highlighting key value
  - Relevance scoring: Score how well applicant matches event theme/audience
  - Recommendation: Suggest approve/reject with reasoning based on event criteria
  - Highlight unique value: Identify what makes this applicant special (Ivy League, startup founder, etc.)
- **LLM Relationship & Network Mapping**
  - Mutual connections potential: Analyze company, school, field overlaps
  - Complementary profiles: Match "can_offer" with "looking_for" across users
  - Influence indicators: Identify thought leaders, serial entrepreneurs, notable investors
- **LLM Data Enrichment from External Sources**
  - LinkedIn profile parsing: If LinkedIn URL provided, extract additional context
  - Company intelligence: Enrich company info (size, funding stage, industry)
  - Education verification: Cross-reference school names, verify degree programs
  - Professional validation: Flag inconsistencies (e.g., claimed C-level at unknown company)
- **LLM Searchable Knowledge Extraction**
  - Skills inventory: Parse "can_offer" into structured skills database
  - Interest mapping: Create interest taxonomy from "professional_interests"
  - Geographic clustering: Use city/timezone for regional network analysis
  - Industry classification: Auto-categorize into healthcare sub-domains (pharma, medtech, digital health, etc.)

### Phase 3: Enhanced Features
- Network statistics and analytics
- Contact recommendations
- Event recommendations
- Advanced permissions
- Bulk operations

### Phase 4: Polish & Scale
- Performance optimization
- Mobile responsiveness improvements
- Advanced UI/UX enhancements
- Integration capabilities
- Analytics dashboard

## Access Control Summary

### Regular Users (role: 'member')
- ✅ View and edit own profile
- ✅ Browse and view event list
- ✅ Apply for events (submit applications)
- ✅ View own application status (pending, approved, rejected)
- ✅ View approved events
- ❌ Cannot view contacts
- ❌ Cannot access network visualization
- ❌ Cannot access manager dashboard
- ❌ Cannot approve/reject applications

### Managers (role: 'manager', 'organizer', 'admin')
- ✅ All regular user permissions
- ✅ View all organization contacts (contact database)
- ✅ Manage contacts (add, edit, delete)
- ✅ Screen/filter contacts by tags, keywords, company, job title, event, etc.
- ✅ Export contacts with custom field selection (CSV, Excel, JSON)
- ✅ Save and reuse filter presets
- ✅ Access network visualization
- ✅ View organization-wide network statistics
- ✅ Access manager dashboard
- ✅ Create and manage events (organizers/admins)
- ✅ Review and approve/reject event applications
- ✅ View all applications for events
- ✅ Check-in attendees at events
- ✅ Mark attendance (attended/absent) for events
- ✅ View attendance lists and reports
- ✅ View complete event history for any user (application status + attendance status)
- ✅ View user participation statistics

## Questions to Consider

1. **Multi-tenancy**: Should users be able to belong to multiple organizations?
2. **Event Privacy**: All events are closed-door with application/approval. Should there be different approval workflows for different event types?
3. **Contact Ownership**: Are contacts organization-owned or manager-owned? (Currently organization-owned based on design)
4. **Data Export**: Should managers be able to export organization contact data?
5. **Notifications**: Real-time or email-only initially?
6. **File Uploads**: Where to store event images and profile pictures?
7. **Search**: Full-text search requirements? (PostgreSQL full-text or Elasticsearch)
8. **Internationalization**: Multi-language support needed?
9. **Manager Promotion**: How do users become managers? Admin assignment only?
10. **Application Review**: Should there be multiple approvers or just one? Any approval workflow (e.g., require 2 approvals)?
11. **Application Form**: What fields should be required in the application form? Customizable per event?
12. **Rejection Reasons**: Should rejection reasons be mandatory or optional? Can users appeal rejections?
13. **Onboarding Completion**: With quick 4-minute onboarding, users can start applying immediately. Should there be any restrictions? Should detailed profile completion be incentivized?
14. **LLM Enrichment**: Real-time on profile update or batch processing? What's the cost/performance tradeoff?
15. **Profile Completeness**: Should there be incentives for completing full profile? What's the minimum required?
16. **Data Validation**: How to handle LLM extraction errors? Human review process?
17. **Enrichment Updates**: How often to re-run LLM enrichment? On every profile update or periodic batch?
18. **Privacy & LLM**: How to ensure LLM processing respects consent settings? Data retention policies?

