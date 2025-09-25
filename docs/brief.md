# Project Brief: Shtetl

## Executive Summary
Shtetl is an open-source community data hub that gives Jewish kehilas (community) a single place to publish and manage zmanim, davening and shiurim times, seating plans, shaylos and shul content, and other communal services. It tackles fragmented communication by letting each synagogue control its own space while offering congregants unified access through mobile apps, MCP integrations, and automation hooks. The platform’s core promise is timely, actionable visibility into zmanim, davening and shiurim times, and alerts that keep the entire community connected.

## Problem Statement
Local Jewish communities juggle dozens of unstructured channels—WhatsApp broadcasts, hallway announcements, sms, email threads—to keep track of minyan schedules, shiur rotations, and communal services. Because every synagogue (and often individual gabbaim) maintains its own version of “truth,” members struggle to keep track of the latest times as they usually come in a printed format that might be hanging somewhere but not accessible on the go when you need it. Times change from week to week or even daily making it difficult to remember, track or set reminders. Gaboim burn hours syncing spreadsheets, and calendars, emails and sms , yet still face panicked calls minutes before Shacharis asking whether there’s a 6:20 or 6:30 start. There is no easy wat expose APIs that community developers can extend. As expectations for automation grow — such as turning on air conditioning 30 minutes before first minyan, triggering security lighting, or pushing location-aware alerts.

## Proposed Solution
Shtetl delivers a modular, open-source platform that lets each synagogue run its own managed space while contributing to a shared community-wide data backbone. Administrators get a synagogue-specific control panel to publish minyan schedules, shiurim, alerts, simchas etc, and optionally zmanim. Congregants access the same trusted source through mobile apps, opt-in subscriptions for SMS and email, and programmable channels (MCP servers, Zapier, smart facility triggers) that translate communal data into timely reminders or physical actions. Because the toolkit is community-owned, developers can extend integrations, crowdsource improvements, and ensure every update respects local minhagim. The result is a reliable, self-sustaining hub that keeps schedules in sync, empowers automation, and scales with the community’s needs.

## Target Users
### Primary User Segment: Congregation Members
- **Demographic/Firmographic Profile:** Adults in small-to-medium Jewish communities; includes working professionals, parents planning family participation, retirees prioritizing daily minyan attendance, and occasional visitors needing accurate info.
- **Current Behaviors & Workflows:** Subscribe to multiple WhatsApp groups, check printed bulletins, ask neighbors or gabbaim for confirmation, rely on word-of-mouth updates.
- **Needs & Pain Points:** Want reliable, real-time zmanim, minyan, and shiur schedules; frustrated by scattered updates, missed reminders, and uncertainty about location or service type.
- **Goals:** Show up on time for services, plan learning schedules, coordinate family logistics, receive alerts for schedule changes or special events.

## Goals & Success Metrics
### Business Objectives
- Increase synagogue transparency by centralizing 80% of communal schedule updates into Shtetl within 6 months of launch.
- Reduce administrator workload by cutting time spent on manual notifications by 40% per participating synagogue within the first quarter.
- Foster open-source adoption with at least three community-driven feature contributions in the first year.

### User Success Metrics
- At least 70% of active congregants subscribe to personalized minyan or shiur alerts.
- Average time-to-awareness for schedule changes drops below 10 minutes from publication.
- 60% of surveyed users report higher confidence in schedule accuracy.

### Key Performance Indicators (KPIs)
- **Synagogue Onboarding Rate:** Number of active synagogue spaces created vs. outreach targets (goal: 15 by month 6).
- **Automation Engagement:** Count of automation rules executed per week (goal: 200 triggers by month 6).
- **Contribution Velocity:** Pull requests merged per quarter from community contributors (goal: 5+ after initial release).

## MVP Scope
### Core Features (Must Have)
- **Synagogue Spaces:** Dedicated admin portals for each synagogue to manage schedules, events, and announcements with fine-grained permissions.
- **Prayer Time Scheduling:** Daily minyan setup with zmanim-aware logic, recurring templates, and exception handling for holidays.
- **Shiur & Event Listings:** Publish learning sessions and communal events with categories, speakers, and location metadata.
- **User Subscriptions & Alerts:** Allow congregants to subscribe to specific minyanim or shiur categories and receive push/email notifications.
- **Automation Hooks:** Integrate with MCP servers/Zapier to trigger facilities actions (e.g., HVAC on/off) based on schedule data.
- **Mobile App Access:** Provide iOS/Android front ends for browsing schedules, configuring reminders, and receiving alerts.

### Out of Scope for MVP
- Advanced donation management or payment processing.
- Complex CRM features beyond basic member directories.
- Full-scale facility resource booking (rooms, equipment) beyond simple availability notes.
- AI-driven personalization or recommendation engines.
- Multi-language translations beyond core English/Hebrew interface.

### MVP Success Criteria
Shtetl MVP is successful when at least five synagogues actively maintain their schedules through the platform, congregants rely on the mobile app or alerts for daily minyan attendance, and the automation hooks are powering at least one real-world facility action per participating synagogue, with feedback indicating improved schedule confidence.

## Post-MVP Vision
### Phase 2 Features
- Congregational dashboards.
- Community-wide event discovery with filtering by neighborhood, nusach, accessibility features.
- Shared learning libraries that catalog shiur recordings and source sheets linked to schedules.

### Long-term Vision
Shtetl evolves into the default digital fabric for Jewish communal life—interconnecting synagogues, schools, and organizations through shared data standards, interoperable APIs, and community-built modules. It supports global deployment with localized minhagim, allows cross-community collaboration (e.g., visiting scholar circuits), and integrates with smart-city infrastructure for security and logistics.

### Expansion Opportunities
- Partnerships with manufacturers of synagogue HVAC/security systems for native integrations.
- Regional federation deployments providing multi-synagogue oversight.
- Developer marketplace for third-party modules (e.g., Kaddish reminders, lifecycle event tracking).
- Educational institutions syncing class schedules and extracurricular programming.

## Technical Considerations
### Platform Requirements
- **Target Platforms:** Web admin console; native mobile apps (iOS/Android) for congregants; integration endpoints for MCP/Zapier connectors.
- **Browser/OS Support:** Modern evergreen browsers for web; iOS 15+/Android 11+ for mobile to leverage current push/automation capabilities.
- **Performance Requirements:** Near-real-time propagation of schedule updates (<30 seconds); automation triggers to execute within 2 minutes of scheduled events.

### Technology Preferences
- **Frontend:** React-based web admin; React Native or Flutter for cross-platform mobile apps.
- **Backend:** Node.js/TypeScript (aligns with automation-friendly ecosystem) with modular service architecture.
- **Database:** PostgreSQL for relational scheduling data plus Redis for caching event timelines.
- **Hosting/Infrastructure:** Cloud-native deployment (e.g., AWS/GCP) with serverless functions handling automation hooks, containerized services for core APIs.

### Architecture Considerations
- **Repository Structure:** Monorepo housing core services, admin front end, mobile clients, and integration adapters for easier coordination.
- **Service Architecture:** API gateway exposing schedule, alert, and automation services; event-driven messaging for automation triggers; plugin framework for community-built modules.
- **Integration Requirements:** REST/GraphQL APIs with webhooks; connectors to MCP servers, Zapier, and facility control systems (HVAC, lighting).
- **Security/Compliance:** Role-based access for synagogue admins; audit trails for schedule edits; secure handling of personal contact data; compliance with regional privacy laws (e.g., GDPR where applicable).

## Constraints & Assumptions
### Constraints
- **Budget:** Bootstrap/open-source funding; rely on volunteer contributions and modest operational budget for hosting and core maintenance.
- **Timeline:** Aim to release MVP within 6 months, aligned with upcoming High Holiday season when scheduling pressures peak.
- **Resources:** Core team of a few developers plus volunteer contributors for integrations; synagogue admins providing domain input.
- **Technical:** Must accommodate diverse synagogue data formats and handle zmanim calculations with halachic accuracy across time zones.

### Key Assumptions
- Synagogues are willing to centralize schedules if they retain autonomy over their space and branding.
- Community members will adopt mobile/apps and alert subscriptions if information remains accurate and timely.
- Volunteer developers will contribute integrations if the project offers clear APIs and governance.
- Facility teams can interface with MCP/Zapier-compatible controllers for automation.

## Risks & Open Questions
### Key Risks
- **Data Accuracy Drift:** Without disciplined admin workflows, stale or conflicting updates could erode trust and cause users to revert to old channels.
- **Automation Misfires:** Incorrect automation rules (e.g., HVAC on at wrong time) could waste resources or create safety issues, prompting backlash.
- **Adoption Resistance:** Some synagogues may resist centralization due to fear of losing control or misaligned digital readiness. Also there is Internet dependance which some Shuls might object to. An optional SMS, or telephone interface can be built to mitigate this
- **Volunteer Burnout:** Reliance on community contributors could stall integrations or maintenance if onboarding/support isn’t strong.

### Open Questions
- How will we onboard synagogues efficiently, including training and data migration from spreadsheets/WhatsApp?
- What governance model ensures quality control over community contributions and integrations?
- Which communication channels (push, SMS, email) are mandatory at launch vs. optional?
- How do we handle varied halachic interpretations (e.g., zmanim calculations) across communities?

### Areas Needing Further Research
- Benchmarking successful communal scheduling systems to identify best practices.
- Evaluating automation hardware vendors used by synagogues for HVAC, lighting, security.
- Understanding legal/privacy requirements for storing congregant contact data in different regions.
- Assessing user appetite for cross-synagogue discovery features vs. synagogue-specific views.

## Appendices
- **A. Research Summary:** _Not yet provided._
- **B. Stakeholder Input:** _Not yet provided._
- **C. References:** `docs/prd.md`; `docs/architecture/*`; MCP & Zapier documentation (links TBD).

## Next Steps
1. Confirm synagogue onboarding plan and create a repeatable data migration/import template.
2. Validate automation hardware compatibility list (HVAC, lighting, security) with 2-3 pilot synagogues.
3. Define governance and contribution guidelines for community developers, including code review process.
4. Conduct user interviews with congregants to prioritize notification channels and alert preferences.

### PM Handoff
This Project Brief provides the full context for Shtetl. Please start in PRD Generation Mode, review the brief thoroughly to work with the user to create the PRD section by section as the template indicates, asking for any necessary clarification or suggesting improvements.

