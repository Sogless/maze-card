\# MazeCard Website — Product Spec (Build Instructions)

\#\# Purpose  
Build the MazeCard marketing website and onboarding flows for:  
1\) Cooperatives (create cooperative profile \+ schedule demo)  
2\) Merchants (apply to join merchant network)

The site must clearly explain MazeCard’s offering and convert visitors into qualified leads.

\#\# Key product facts (must be accurately reflected)  
\- MazeCard is "Credit Card as a Service" for cooperatives.  
\- Cards are PHYSICAL and can be Mastercard or Verve.  
\- Cards are issued by partner commercial banks who hold funds and white-label the cards to MazeCard.  
\- Limits & credit scoring are based on member contribution history and a minimum threshold of consecutive monthly contributions.  
\- Limits can also be defined by the SLA between MazeCard and the cooperative.  
\- Members pay 0% interest if monthly spend is repaid before the 28th of each month.  
\- Default policy:  
  \- Flat default fee: ₦5,000  
  \- Plus: 1% of amount owed in first month after default, 2% in second month, 3% in third month and beyond.  
  \- On default: no more credit until fully repaid.  
  \- After repayment post-default: credit limit is halved.  
  \- Any user that defaults 3 times within a 6-month period is blacklisted.  
\- Repayments/collections happen via MazeCard app or coop management platforms like Akilaah.  
\- MazeCard operates an invite-based merchant network.  
\- Merchant settlement is T+40 to T+60.  
\- KYC is done through MazeCard app or platforms like Akilaah.

IMPORTANT LEGAL/TRUST LINE:  
Every relevant page must include a note similar to:  
"Cards are issued by partner banks. MazeCard provides the platform for eligibility, limits, repayment, and collections."

\#\# Design / Theme  
\- Theme aligns closely with hydrogenpay.com (modern fintech layout patterns).  
\- Use a dark theme: deep charcoal background, slate cards, soft borders.  
\- Accent color: "Maze Yellow" (darker yellow than typical bright yellow).  
  \- Define as a design token (example): \--maze-yellow: \#D4A100 (you can tweak slightly, but keep it darker than pure yellow).  
\- Buttons:  
  \- Primary button uses Maze Yellow background with dark text.  
  \- Secondary button is outline with Maze Yellow border and hover glow.  
\- Typography:  
  \- Big hero headline (48–64px on desktop), strong subheadline.  
  \- Use short paragraphs and bullets; plenty of whitespace.  
\- Animations:  
  \- Subtle hover effects on cards and buttons; no heavy animations.

\#\# Tech & Architecture (recommended)  
\- Use Next.js (App Router) \+ TypeScript \+ Tailwind.  
\- Use a simple server-side persistence for forms:  
  \- Option A (preferred): SQLite (via Prisma) for MVP.  
  \- Option B: JSON file storage (ONLY if absolutely necessary; less ideal).  
\- Auth for cooperative dashboard:  
  \- Basic email \+ password auth (MVP) OR magic link (if faster).  
  \- Protect dashboard routes.  
\- Form validation:  
  \- Client \+ server validation, show friendly inline errors.

\#\# Sitemap / Routes  
Public pages:  
\- \`/\` Home  
\- \`/cooperatives\` For Cooperatives  
\- \`/merchants\` For Merchants  
\- \`/how-it-works\`  
\- \`/pricing\`  
\- \`/resources\`  
\- \`/resources/faq-cooperatives\`  
\- \`/resources/faq-merchants\`  
\- \`/resources/risk-repayment-policy\`  
\- \`/company/about\`  
\- \`/company/contact\`  
\- \`/signin\`

Onboarding flows:  
\- \`/cooperative/create\` Cooperative Profile Creation (multi-step)  
\- \`/cooperative/dashboard\` Cooperative Admin Dashboard (protected)  
\- \`/merchant/apply\` Merchant Application

\#\# Core CTAs  
Use consistent CTAs site-wide:  
\- Primary: "Create Cooperative Profile" \-\> \`/cooperative/create\`  
\- Secondary: "Book a Demo" \-\> from anywhere; if logged in \-\> dashboard demo section; else \-\> prompt to create profile first.  
\- Merchant: "Apply to Join the Network" \-\> \`/merchant/apply\`

\#\# Page Content (copy must match the plan below)

\#\#\# HOME (\`/\`)  
Hero:  
\- Headline: "Credit, delivered through cards — built for cooperatives."  
\- Subheadline: "MazeCard is Credit Card as a Service for cooperatives. Offer members structured monthly credit via physical Mastercard or Verve cards—powered by partner banks and managed end-to-end with MazeCard."  
\- Trust line: bank-issued note.  
\- Buttons: Create Cooperative Profile, Book a Demo, "I’m a Merchant" \-\> \`/merchants\`

Sections:  
1\) Outcomes band (no hard numbers; benefits only)  
2\) Two-path cards:  
   \- For Cooperatives (bullets \+ CTA)  
   \- For Merchants (bullets \+ CTA)  
3\) "How MazeCard Works" (4 steps)  
4\) Features grid (6 cards):  
   \- Eligibility & Limits  
   \- 0% Interest  
   \- Default Controls  
   \- Collections Anywhere  
   \- Merchant Network  
   \- Bank-Backed Issuance  
5\) CTA band: "Ready to launch cooperative credit with card rails?"

Footer:  
\- Products, Resources, Company, Legal placeholders

\#\#\# FOR COOPERATIVES (\`/cooperatives\`)  
Hero:  
\- "Give your members credit—without building banking infrastructure."  
\- Subheadline about card-based disbursement, contribution-based limits, automated enforcement.  
\- Buttons: Create Cooperative Profile, Book a Demo

Sections:  
1\) "What you get" 3 pillars:  
   \- Card-based Credit Disbursement  
   \- Credit Rules that Match Cooperative Reality  
   \- Recovery Built In  
2\) Eligibility & Limits explanation (contributions \+ SLA flexibility)  
3\) Repayment & Defaults (must be transparent and accurate):  
   \- Repayment date: 28th  
   \- 0% interest if repaid by 28th  
   \- Default fees: ₦5,000 \+ 1% month1, 2% month2, 3% month3+  
   \- Enforcement: suspend credit until repaid; limit halved after; 3 defaults in 6 months \-\> blacklisted  
4\) Operations & Integrations:  
   \- MazeCard app repayments  
   \- Akilaah supported (flag-based)  
   \- KYC options  
5\) Member experience summary  
6\) Onboarding steps (1–5) \+ CTA

\#\#\# FOR MERCHANTS (\`/merchants\`)  
Hero:  
\- "Get invited into a network designed to drive consistent spend."  
\- Mention invite-based network and predictable settlement window.  
\- Buttons: Apply to Join, Talk to Sales (to contact form)

Sections:  
1\) How network works (invite-based) \+ settlement T+40 to T+60  
2\) Why merchants join (bullets)  
3\) Who should apply (categories list; keep flexible)  
4\) Merchant onboarding steps (1–5) \+ CTA

\#\#\# HOW IT WORKS (\`/how-it-works\`)  
Hero:  
\- "A complete credit cycle—built for cooperative lending."

Flow (6 steps):  
1\) Cooperative setup  
2\) Member eligibility (contributions)  
3\) Limit assignment (model or SLA)  
4\) Card issuance (Mastercard/Verve via partner bank)  
5\) Monthly spend  
6\) Repayment & enforcement

Controls section:  
\- suspend on default  
\- limit halving  
\- blacklist policy  
\- multi-channel collections

\#\#\# PRICING (\`/pricing\`)  
Sales-led, no numeric pricing.  
\- Headline: "Pricing that matches cooperative scale."  
\- Pricing components list:  
  \- Program setup  
  \- Card issuance  
  \- Platform usage  
  \- Merchant network services  
\- Note: "Final pricing is defined in your SLA."  
\- CTA: Book a Demo

\#\#\# RESOURCES (\`/resources\`)  
Index page linking to:  
\- FAQ (Cooperatives)  
\- FAQ (Merchants)  
\- Risk & Repayment Policy

\#\#\#\# FAQ Cooperatives (\`/resources/faq-cooperatives\`)  
Include:  
\- Is MazeCard a bank? (No; partner banks issue cards)  
\- How are limits determined? (contributions \+ SLA)  
\- Do members pay interest? (0% if paid by 28th)  
\- What happens on default? (rules)  
\- Can we use existing cooperative platform? (Akilaah supported where applicable)

\#\#\#\# FAQ Merchants (\`/resources/faq-merchants\`)  
Include:  
\- How do I join? (apply; invite-based)  
\- When do I get settled? (T+40 to T+60)  
\- What do I need for onboarding? (business details \+ KYC)

\#\#\#\# Risk & Repayment Policy (\`/resources/risk-repayment-policy\`)  
A clean page restating:  
\- 28th cutoff  
\- 0% interest if on time  
\- default fee ladder and enforcement  
\- blacklist policy  
\- SLA-configurable portions (limits/eligibility)

\#\#\# COMPANY  
About (\`/company/about\`):  
\- "Built to help cooperatives lend responsibly at scale."  
\- Short narrative

Contact (\`/company/contact\`):  
\- Sales/Partnership form (name, email, message, type)  
\- Support placeholder  
\- No fake addresses; use placeholders.

\#\# Forms & Data Model

\#\#\# Cooperative Profile Creation (\`/cooperative/create\`)  
Multi-step form:

Step 1: Cooperative details (required unless noted)  
\- cooperative\_name (required)  
\- registration\_type (optional)  
\- registration\_id (optional)  
\- address (required)  
\- state (optional)  
\- lga (optional)  
\- contact\_name (required)  
\- contact\_role (required)  
\- email (required)  
\- phone (required)

Step 2: Program intent (required)  
\- estimated\_member\_count (required, integer)  
\- pilot\_cohort\_size (required, integer)  
\- preferred\_card\_scheme (required: "Mastercard" | "Verve" | "Either")  
\- uses\_akilaah (required: boolean)  
\- desired\_launch\_timeline (required: enum: "0–30 days" | "30–60 days" | "60–90 days" | "90+ days")

Step 3: Verification uploads (optional MVP)  
\- registration\_proof\_file (optional)  
\- board\_authorization\_file (optional)  
\- admin\_id\_file (optional)

Step 4: Admin account (required)  
\- admin\_password \+ confirm (or magic link flow)  
\- email verification recommended

After completion:  
\- Create a "cooperative" record and an "admin user" record.  
\- Redirect to \`/cooperative/dashboard\`.

\#\#\# Cooperative Dashboard (\`/cooperative/dashboard\`)  
Show:  
\- Profile summary (read-only MVP)  
\- Next steps:  
  \- "Book a Demo" section  
  \- "What to expect on the demo" checklist (3–5 bullets)  
\- Optional: "Edit profile" disabled with "Coming soon"

\#\#\# Demo Scheduling  
Implement one of:  
A) Embed external scheduling widget using env var (e.g., \`NEXT\_PUBLIC\_DEMO\_SCHEDULER\_URL\`)  
B) Internal booking request form:  
\- topic (multi-select)  
\- preferred\_datetime (required)  
\- timezone (auto-detect)  
\- notes (optional)

On submit:  
\- Store booking request in DB.  
\- Show confirmation page/state.

\#\#\# Merchant Application (\`/merchant/apply\`)  
Fields:  
\- business\_name (required)  
\- category (required)  
\- address (required)  
\- contact\_name (required)  
\- email (required)  
\- phone (required)  
Optional:  
\- registration\_id (optional)  
\- kyc\_docs (optional upload)

After submit:  
\- Store record in DB.  
\- Show confirmation state:  
  "Application received. The merchant network is invite-based. Our team will review and reach out."

\#\# Analytics  
Implement event tracking with a simple abstraction (console logging is acceptable in dev; hook for GA/PostHog later).  
Track:  
\- view\_homepage  
\- click\_create\_coop\_profile  
\- submit\_coop\_profile  
\- schedule\_demo\_open  
\- schedule\_demo\_confirmed OR schedule\_demo\_request\_submitted  
\- view\_merchants\_page  
\- submit\_merchant\_application  
\- faq\_viewed  
\- policy\_viewed

\#\# Acceptance Criteria Checklist  
\- All routes exist and match content requirements.  
\- Dark theme \+ Maze Yellow accent is consistent and polished.  
\- Cooperative profile flow works end-to-end and persists data.  
\- Cooperative dashboard is protected and displays submitted data.  
\- Demo scheduling works end-to-end (embed or internal).  
\- Merchant application works end-to-end and persists data.  
\- Resources pages (FAQs \+ policy) match required content.  
\- Responsive layouts for mobile/tablet/desktop.  
\- No broken links; consistent CTAs.  
\- Trust line about partner-bank issuance is present where relevant.

\#\# Developer Notes  
\- Do NOT invent partner bank names or addresses.  
\- Use placeholders for legal pages (privacy/terms) unless provided.  
\- Keep copy exactly as specified, but you may adjust microcopy for clarity without changing meaning.  
\- Prioritize usability and conversion: clear CTAs, short sections, fast load.

