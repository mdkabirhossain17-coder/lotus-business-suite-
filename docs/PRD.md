# STEP_4_MASTER_BUILD_PROMPT_LOTUS_SURGICAL_v1.0.md

# STEP 4 — MASTER BUILD PROMPT v1.0
# LOTUS SURGICAL — AI-POWERED BUSINESS OPERATING & SALES SYSTEM

## ROLE

Act as:

- Lead Product Architect
- Senior Full-Stack Engineer
- Supabase Database Engineer
- Marketing Workflow Architect
- UX/UI Designer
- QA Engineer
- Security Engineer
- AI Systems Architect

You are building a production-minded business operating system for:

**Lotus Surgical**

Business type:

**Healthcare / Surgical / Medical Equipment Sales**

---

## PRIMARY OBJECTIVE

Transform Lotus Surgical's manual business operations into one centralized digital business operating and sales system.

Core system:

**Product → Inventory → Customer → Lead → Sales → Order → Marketing → Customer Support → Analytics → AI Assistance → Automation**

This must be a real, usable, secure, responsive, scalable application — not a static demo.

---

# 1. TECHNOLOGY ARCHITECTURE

## AI App Builder

OnlyAIApp

## Source Control

GitHub

Repository:

`lotus-surgical-business-system`

## Database / Backend

Supabase

Use:

- PostgreSQL
- Supabase Auth
- Supabase Storage
- Row Level Security (RLS)

## Hosting / Deployment

Vercel

---

# 2. CORE MODULE ARCHITECTURE

Build the system as modular components:

### M01 — Dashboard
Business overview and operational summary.

### M02 — Product Management
Products, SKU, category, brand, specifications, pricing and product status.

### M03 — Inventory Management
Stock, stock movements, availability and inventory status.

### M04 — Customer Management
Customer profiles, contact information and customer history.

### M05 — Lead & Inquiry Management
Leads, inquiries, sources, activities and follow-up.

### M06 — Sales / CRM
Sales opportunities, pipeline, follow-ups and conversion.

### M07 — Order Management
Orders, order items, payments, delivery and order status.

### M08 — Product Listing & Content Management
Product descriptions, SEO content, social content, images and approval workflow.

### M09 — Marketing Management
Approved content → marketing activity → review → approval → schedule/publish → track result.

### M10 — Customer Support
Customer issues, conversations, support activities and resolution tracking.

### M11 — AI Assistant / AI Co-Work
AI-assisted research, drafting, analysis, recommendations and operational assistance.

### M12 — Analytics & Business Intelligence
Business KPIs, sales, inventory, customer, lead and marketing intelligence.

### M13 — Automation
Rule-based and AI-assisted workflow automation.

### M14 — User / Role / Permission Management
Users, roles, permissions and access control.

### M15 — Settings & System Administration
System configuration and administrative controls.

---

# 3. CORE BUSINESS FLOW

```text
PRODUCT
   ↓
MARKETING
   ↓
LEAD / INQUIRY
   ↓
SALES / CRM
   ↓
CUSTOMER
   ↓
ORDER
   ↓
INVENTORY
   ↓
DELIVERY
   ↓
AFTER-SALES
   ↓
REPEAT SALES
   ↓
ANALYTICS
   ↓
AI INTELLIGENCE
```

Do not bypass the business flow.

Examples:

Marketing must not directly create an Order.

Correct:

Marketing → Lead → Sales → Order

Inventory must remain connected to Products and Orders.

---

# 4. ARCHITECTURAL LOCK

M01–M15 are the planned system modules.

Build incrementally.

Do NOT silently:

- redesign the architecture
- replace the database
- replace Supabase
- replace GitHub
- replace Vercel
- rewrite completed modules
- create duplicate product/customer/lead/order systems
- delete production data
- drop tables
- rename existing tables without approval
- introduce a completely different framework without approval

If a major architectural change is required:

1. Explain the problem.
2. Explain why it is required.
3. Explain the impact.
4. Propose the smallest possible change.
5. STOP and request approval before making the major change.

If something is not explicitly defined, write:

**Not Explicitly Locked in Current Source**

If two requirements conflict, write:

**CROSS-CHUNK REVIEW FLAG**

Do not guess.

---

# 5. BUILD STRATEGY

Build sequentially:

```text
FOUNDATION
   ↓
AUTH
   ↓
DATABASE
   ↓
PRODUCT
   ↓
INVENTORY
   ↓
CUSTOMER
   ↓
LEAD
   ↓
SALES / CRM
   ↓
ORDERS
   ↓
CONTENT
   ↓
MARKETING
   ↓
SUPPORT
   ↓
AI
   ↓
ANALYTICS
   ↓
AUTOMATION
   ↓
ADMIN
```

For every module:

```text
BUILD
  ↓
TEST
  ↓
QA
  ↓
REPORT
  ↓
GITHUB COMMIT
  ↓
STOP
```

Never automatically continue to the next module.

---

# 6. FOUNDATION — CURRENT BUILD TARGET

For the initial build, implement ONLY the application foundation.

Build:

1. Application shell
2. Responsive navigation
3. Login / authentication foundation
4. Supabase connection
5. User foundation
6. Role foundation
7. Protected routes
8. Dashboard shell
9. Error states
10. Loading states
11. Empty states
12. Security foundation
13. GitHub-ready project structure
14. Vercel deployment readiness

Future modules may appear in navigation as:

**Coming Soon**

Do not implement their business logic yet.

---

# 7. SUPABASE ARCHITECTURE

Supabase is the source of truth for business data.

Use:

- PostgreSQL
- Supabase Auth
- Supabase Storage
- RLS
- migrations
- foreign keys
- indexes
- timestamps
- appropriate constraints

Never put the Supabase service-role key in client/frontend code.

Never expose database passwords.

Never hard-code secrets.

---

# 8. DATABASE SAFETY

Before creating or changing database structures:

1. Inspect the existing schema.
2. Reuse existing tables where possible.
3. Avoid duplicate entities.
4. Use migrations for schema changes.
5. Never drop production tables.
6. Never delete production data.
7. Never silently rename existing tables.
8. Preserve existing relationships.
9. Add indexes where appropriate.
10. Apply RLS to protected business data.

If a new table is necessary but was not explicitly locked:

**CROSS-CHUNK REVIEW FLAG**

Explain:

- Table name
- Purpose
- Fields
- Relationships
- RLS requirements
- Impact

Then STOP before a major migration.

---

# 9. CORE DATA ARCHITECTURE

The planned core entities include:

```text
users
roles
user_roles

categories
brands
suppliers
products

customers

leads
lead_activities

quotes
quote_items

orders
order_items
payments
deliveries
returns

inventory
stock_movements

product_contents
product_images

ai_tasks
ai_outputs

activities
```

Do not create duplicate versions of these entities.

Marketing-specific persistence should be introduced only when necessary and should trigger a review if it changes the locked architecture.

---

# 10. AUTHENTICATION

Use Supabase Auth.

Initial authentication flow:

```text
LOGIN
  ↓
SUPABASE AUTH
  ↓
AUTHENTICATED USER
  ↓
USER PROFILE
  ↓
ROLE
  ↓
AUTHORIZED DASHBOARD
```

Implement:

- Login
- Logout
- Protected routes
- Session handling
- Unauthorized access handling

Do not rely only on frontend UI hiding for security.

---

# 11. ROLE ARCHITECTURE

Planned roles:

- ADMIN
- MANAGER
- SALES
- INVENTORY
- CONTENT
- SUPPORT

Initial role permissions must be enforced through the existing authorization architecture and Supabase RLS.

Do not create a complex permission engine unless required.

---

# 12. SECURITY RULES

Implement:

- Supabase RLS
- Role-based authorization
- Protected routes
- Server-side validation where applicable
- Input validation
- Database constraints
- Secure environment variables
- Audit trail for important business actions

Never commit:

```text
.env
.env.local
database passwords
service-role keys
private API keys
access tokens
```

Create:

`.env.example`

with variable names only.

---

# 13. ENVIRONMENT VARIABLES

Use environment variables for Supabase and other external services.

Example:

```env
NEXT_PUBLIC_SUPABASE_URL=YOUR_SUPABASE_PROJECT_URL
NEXT_PUBLIC_SUPABASE_PUBLISHABLE_KEY=YOUR_SUPABASE_PUBLISHABLE_KEY
```

Do not place actual secret values in source code.

Do not expose secret/service-role credentials to the browser.

---

# 14. UI / UX

Create a professional business application for Lotus Surgical.

Requirements:

- Clean
- Simple
- Fast
- Responsive
- Mobile-friendly
- Desktop-friendly
- Clear navigation
- Clear forms
- Clear tables
- Clear status indicators
- Accessible controls
- Confirmation for destructive actions

Use the existing application design system if one exists.

Do not redesign the entire product unnecessarily.

Do not prioritize visual decoration over operational usability.

---

# 15. DATA PRINCIPLE

Never use fake production metrics.

If real data does not exist:

Use:

`0`

or:

`—`

Do not fabricate:

- sales
- revenue
- stock
- customers
- leads
- orders
- marketing performance
- conversion rates

Demo/sample data must be clearly identified as sample data and must never be presented as real business data.

---

# 16. AI PRINCIPLE

AI assists humans.

AI may:

- analyze
- summarize
- classify
- extract
- draft
- recommend
- prioritize
- detect patterns
- generate
- assist workflows

AI must not autonomously perform sensitive business actions without appropriate authorization.

Examples requiring human control:

- Customer-facing publication
- Price changes
- Orders
- Refunds
- Critical inventory actions
- Financial actions
- Sensitive customer communications

---

# 17. M08 → M09 MARKETING PRINCIPLE

Marketing must use approved M08 product content.

Correct workflow:

```text
M08 APPROVED CONTENT
       ↓
MARKETING ASSET
       ↓
CHANNEL
       ↓
MARKETING ACTIVITY
       ↓
HUMAN REVIEW
       ↓
APPROVAL
       ↓
SCHEDULE / PUBLISH
       ↓
LEAD
       ↓
M05
       ↓
M06 SALES
       ↓
M07 ORDER
```

AI-generated content must not automatically become approved production content.

---

# 18. CONTENT SAFETY

For healthcare / surgical equipment:

Never fabricate:

- medical claims
- clinical evidence
- certifications
- testimonials
- reviews
- specifications
- guarantees
- discounts
- pricing
- availability
- product benefits not supported by source data

If information is missing:

**Do not guess.**

Use:

`Information not available in current product data.`

Marketing language must be commercially useful but factually grounded.

Do not turn product marketing into unauthorized diagnosis or doctor-style treatment advice.

---

# 19. EXTERNAL INTEGRATIONS

Do not create autonomous integrations with:

- Facebook / Meta
- WhatsApp
- Google Ads
- Email providers
- Marketplaces
- Payment platforms

unless explicitly requested and the required API credentials and architecture are available.

Never claim that an external platform has been published to unless an actual integration confirms it.

---

# 20. GITHUB

Use:

`lotus-surgical-business-system`

GitHub is the source-code and version-control source of truth.

Use meaningful commits.

Initial foundation commit:

```text
feat: initialize Lotus Surgical application foundation
```

Never commit secrets.

---

# 21. VERCEL

Vercel is the deployment platform.

The application must be deployable on Vercel.

Verify:

- Production build
- Environment variables
- Supabase connection
- Authentication
- Protected routes
- No build errors
- No exposed secrets

After a successful deployment, verify the live application.

---

# 22. FOUNDATION QA GATE

Test:

### TEST 01
Open the application.

Expected:
Application shell loads.

### TEST 02
Open Login.

Expected:
Login UI works.

### TEST 03
Authenticate with Supabase.

Expected:
User session is created.

### TEST 04
Open protected route without authentication.

Expected:
User is redirected/blocked.

### TEST 05
Login again.

Expected:
Authorized dashboard opens.

### TEST 06
Logout.

Expected:
Session ends.

### TEST 07
Refresh browser.

Expected:
Session behavior is correct.

### TEST 08
Check Supabase connection.

Expected:
No connection errors.

### TEST 09
Check mobile layout.

Expected:
No broken layout.

### TEST 10
Check loading state.

Expected:
Clear loading feedback.

### TEST 11
Check empty state.

Expected:
Clear empty-state message.

### TEST 12
Check error state.

Expected:
Clear error message.

### TEST 13
Check security.

Expected:
No secret exposed in frontend.

### TEST 14
Check GitHub.

Expected:
Code committed without secrets.

### TEST 15
Check Vercel.

Expected:
Production build/deployment succeeds.

---

# 23. REGRESSION RULE

When later modules are added, verify that previously completed modules still work.

Never break:

- Authentication
- Product
- Inventory
- Customer
- Lead
- Sales
- Orders
- Product Content
- Marketing

when adding new modules.

---

# 24. ERROR HANDLING

Every module must eventually support:

- Loading state
- Empty state
- Error state
- Validation feedback
- Success feedback
- Permission denied state
- Confirmation for destructive actions

Errors should be understandable to non-technical business users.

---

# 25. PERFORMANCE

Build with production usability in mind.

Avoid:

- unnecessary database queries
- duplicate requests
- unnecessary re-renders
- loading entire datasets when pagination is appropriate
- oversized assets
- unnecessary dependencies

Use indexes for frequently queried database fields where appropriate.

---

# 26. RESPONSIVE DESIGN

The application must work on:

- Mobile
- Tablet
- Desktop

Priority:

1. Business workflow usability
2. Readability
3. Form usability
4. Navigation
5. Performance

---

# 27. CURRENT STOP CONDITION

For the initial execution:

Build ONLY:

- Application shell
- Navigation
- Authentication
- Supabase connection
- User foundation
- Role foundation
- Protected routes
- Dashboard shell
- Security foundation
- Error/loading/empty states
- GitHub-ready structure
- Vercel readiness

Do NOT build the full business modules yet.

After the foundation passes QA:

STOP.

---

# 28. REQUIRED FINAL REPORT

After completing the current foundation, report exactly:

## 1. M01 Foundation Status

## 2. Files Created / Modified

## 3. GitHub Status

## 4. Supabase Connection Status

## 5. Authentication Status

## 6. User / Role Foundation Status

## 7. Security / RLS Status

## 8. Vercel Readiness / Deployment Status

## 9. QA Test Results

## 10. Errors

## 11. Warnings

## 12. Architecture Changes

If none:

`No architecture changes.`

If something was not explicitly locked:

`Not Explicitly Locked in Current Source`

If conflict exists:

`CROSS-CHUNK REVIEW FLAG`

## 13. Known Limitations

## 14. Next Recommended Step

Then STOP.

---

# 29. MASTER RULE

The application must remain:

**Business-first + Data-driven + Secure + Modular + Human-controlled + AI-assisted + Production-minded**

Most important architecture:

```text
ONLYAIAPP
    ↓
GITHUB
    ↓
VERCEL
    ↓
SUPABASE
```

Business system:

```text
PRODUCT
    ↓
INVENTORY
    ↓
CUSTOMER
    ↓
LEAD
    ↓
SALES
    ↓
ORDER
    ↓
CONTENT
    ↓
MARKETING
    ↓
SUPPORT
    ↓
AI
    ↓
ANALYTICS
    ↓
AUTOMATION
```

Do not silently redesign the locked architecture.

Do not fabricate data.

Do not expose secrets.

Do not bypass human approval.

Build one module at a time.

BUILD → TEST → QA → REPORT → COMMIT → STOP.