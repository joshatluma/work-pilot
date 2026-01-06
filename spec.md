# Work Pilot

## Vision

A personal AI assistant for Josh Gill (People Systems, Analytics & AI Automation at Luma AI) that handles day-to-day work tasks autonomously. Give it any task and it takes care of it - from internal coordination to data pulls to meeting prep.

## User Context

**Role:** People Systems, Analytics & AI Automation at Luma AI (Series C)
- Architects the operating system for Luma's people function
- Merges Talent Operations with AI Process Engineering
- Gets requests from anyone in the company (not just hiring managers)
- Already building AI-native recruiting infrastructure (Talent OS v2, Velocity Detective, Luma Key)

**High-Toil Areas:**
- Internal coordination (cross-team syncs, Slack threads, status updates)
- Data/reporting (metrics, dashboards, ATS/HRIS reconciliation)
- Process execution (workflows, automations, exception handling)

**What This Is NOT:** Team infrastructure or candidate communication automation (those are handled by existing systems)

---

## Core Principles

### Identity
- **Transparent AI Proxy**: Always disclose "sent by Josh's AI assistant" - never impersonate

### Trust Model
- **Graduated Autonomy**: Start with human approval on everything, user controls when to reduce oversight
- **Tiered by Stakes**: High autonomy for low-stakes once trust is earned, strict gates for consequential actions
- **Draft Everything**: All external communications queued for review before sending

### Data Access
- **Read-Mostly**: Can read/analyze most data; write/update actions require explicit approval
- **Audit Logging**: Complete record of every action taken and data accessed

### Error Handling
- **Root Cause Analysis**: When wrong, dig into why and create explicit rules to prevent recurrence
- **Alert Immediately**: Technical failures (API down, auth expired) notify right away

---

## Interface Design

### Primary Interface: Command Center
- **Mental Model**: Task inbox + Agent workspace hybrid
  - See incoming tasks, process/delegate/complete them
  - Watch what the AI is working on, planning, thinking
- **Mobile Essential**: Must review/approve tasks on the go
- **Platform**: Cloud-hosted service (accessibility priority)

### Notifications
- **Smart Interrupts**: Real-time alerts for urgent/time-sensitive, batched digests for everything else

### Visibility
- **Summary + Exceptions**: Brief summary of approach, detailed alerts only for unusual situations

### Editing Workflow
- **Both Modes**: Quick edits done directly in interface; bigger changes via feedback loop regeneration
- **Light Versioning**: Keep last few versions for reference, auto-cleanup old ones

---

## Autonomy & Proactivity

### Task Handling
- **Always Clarify**: Ask questions before starting when task is vague - never assume
- **Always Escalate Conflicts**: Surface all priority conflicts for user resolution
- **Ask for Missing Info**: Never proceed without needed information

### Proactive Behavior
- **Proactive with Guardrails**: Can initiate low-stakes tasks autonomously, suggests high-stakes ones
- **24/7 with Smart Timing**: Always running, but delays non-urgent external comms to appropriate hours

### Long-Running Tasks
- **Async Execution**: Run full workflows, send progress updates, only pause if blocked

---

## Context & Memory

### Onboarding
- **Hybrid Bootstrapping**: Structured initial interview + passive observation of work patterns over time

### Memory
- **Full Persistent Memory**: Remember everything - conversations, decisions, context, relationships - like a real assistant

### Learning
- **Multi-Channel**: Explicit corrections, accept/reject behavioral signals, and periodic active feedback

### Boundaries
- **Hard Limits**: Refuse and redirect when outside capabilities/domain - suggest who/where to go instead

---

## Communication Style

### Tone
- **Context-Driven**: Adapt based on situation (urgent vs. casual, good news vs. bad news)

### Third-Party Requests
- **Triage to User**: Queue external requests (e.g., someone DMs the bot) for user review - don't respond directly

---

## Technical Architecture

### AI Backbone
- **Gemini (Google)**: Leverage existing Workspace account and API key

### Tech Stack Preference
- **Google Ecosystem**: GCP, Workspace APIs, aligned with existing infrastructure

### Authentication
- **OAuth per Service**: Standard OAuth flows for each integration (Slack, Google, ATS, etc.)

### Data Freshness
- **Cached Acceptable**: Hours-old data fine for most queries; explicit requests for real-time when needed

---

## Integrations (Priority Order)

### Phase 1 - Core
1. **Slack**: DMs + designated key channels + all @mentions
2. **Google Calendar**: Meeting context and scheduling
3. **Google Docs/Drive**: Document access and creation
4. **Gmail**: Email drafting and triage

### Phase 2 - Data
- ATS integration (read access for pipeline data)
- HRIS integration (read access for employee data)

### MVP Approach
- **Breadth First**: Connect to many systems with basic capabilities before going deep

---

## Priority Use Cases

### 1. Slack Triage
- Monitor DMs, key channels, and @mentions
- Surface what needs attention
- Draft responses for review

### 2. Meeting Prep
- Comprehensive synthesized briefs including:
  - Who's attending, recent interactions, relevant docs/threads
  - Key questions to answer, decisions to make, follow-ups
  - Relationship context, communication style notes

### 3. Data Pulls
- On-demand metrics from ATS/HRIS
- Pipeline status, headcount data, hiring velocity

### 4. Internal Coordination
- Draft status updates and sync messages
- Pull relevant data for personalized communications
- Queue all for review before sending

---

## Security & Privacy

### Primary Safeguard
- **Complete Audit Logging**: Every action, every data access, fully recorded

### Concerns Addressed
- Trust/accuracy: Graduated autonomy model with approval gates
- Security/privacy: Read-mostly access, audit trails, OAuth-based auth

---

## Success Criteria (30 days)

1. **Time Saved**: Measurably less time on routine coordination/data tasks
2. **Mental Load Reduced**: Less cognitive burden from tracking and remembering
3. **Quality Output**: Better work through focus on high-value activities

---

## Expected Usage

- **Volume**: 5-20 tasks delegated per day
- **Nature**: Personal assistant layer (separate from team infrastructure)
