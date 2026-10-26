# Building an internal operating portal for a manufacturer

I spent 2026 as the AI strategist at **The Griff Network**, a specialty-materials converter. My job was to turn how the business actually runs into software the whole company uses, and to build it with AI as the engineering team.

The company's code is private, so this page tells the story and shows the shape of the work. It contains no company data, no customer names and no code.

**Live page:** https://srkrukowski.github.io/griff-network-work/

## The short version

- **One internal portal**, one Google sign-in, about a dozen apps that share one company record of customers, contacts and orders.
- **Over 3,000 commits in seven months** (April to October 2026), built with Claude Code, with every change reviewed and tested before it shipped.
- **Connected to the systems the business already runs on**: Epicor (orders, parts, inventory) and Zoho (sales). The portal captures work and keeps both in step.
- **Built for non-technical users**: plain-English screens, no raw database words, phone-width layouts, and clear states for empty, loading and error.

## What the portal does

| App | What it is |
|---|---|
| Home | A personal start page: what is waiting on me today |
| Leads | A desk that turns inbound email, web forms and chat into worked leads, with a stage ladder and an inquiry reader |
| Quality | Customer complaint handling from report to resolution, with hand-offs, alerts and a living report |
| Trade Shows | Planning, booth staffing and a phone app for scanning contacts on the floor |
| Visitors | A lobby check-in and visit lifecycle |
| New Product Launch | A workflow for launching a product across departments |
| Hiring | An applicant tracking flow |
| Supplier Intelligence | Finding and verifying who supplies a material |
| Finance reporting | Read-only reporting views fed from the ERP mirror |
| Admin | One place for roles, access, automations and system health |

## How it was built

- **Design before code.** Every new screen started as one clickable mockup that I approved before any plan or build.
- **Best practice by product type.** For each app I named what kind of product it is (an ATS, a complaint tracker, a check-in app) and applied what the best of that kind do.
- **Safe by default.** Three access levels per app, row-level security on every table, an audit trail on records that matter, confirmation on anything destructive, and a "view as" mode for admins.
- **An ERP mirror.** A nightly copy of Epicor in a separate database so reporting and AI sessions never touch the live system.
- **Cost and risk gates.** Anything that spends money, writes to production or reaches outside the company needs an explicit go first.

## Stack

Next.js and TypeScript, Supabase (Postgres, row-level security, scheduled jobs), Vercel, Epicor, Zoho CRM, Claude Code.

## Contact

[ScottKrukowski.com](https://scottkrukowski.com) · [The Wise Operator](https://thewiseoperator.com)
