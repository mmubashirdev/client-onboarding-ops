# GitHub Copilot Custom Instructions for ClientOps

## Project Context
ClientOps is an automated client management, onboarding, and PDF generation tool built for MERN stack developers. It automates Scope of Work (SOW) documents, project milestones, invoices, and handoffs.

## Tech Stack Guidelines
- **Frontend:** React.js (Functional components, custom Hooks) + Tailwind CSS
- **Backend:** Node.js + Express.js (REST API architecture with controller-service pattern)
- **Database:** PostgreSQL + Prisma
- **PDF Engine:** @react-pdf/renderer or HTML-to-PDF generation tools

## Code Style & Architecture Conventions
- **JavaScript Standard:** Use modern ES6+ syntax (async/await, destructuring, arrow functions). Avoid `var`.
- **API Responses:** Standardize all backend JSON responses using the structure:
  `{ success: boolean, data?: any, error?: string }`
- **Error Handling:** Always wrap async Express route controllers in try/catch blocks or use a central `asyncHandler` middleware.
- **Component Styling:** Use utility-first Tailwind CSS classes. Avoid inline style objects unless calculating dynamic layout dimensions for PDFs.
- **Data Validation:** Validate incoming request payloads (using Zod) before saving to database models.

## ClientOps Business Logic Constraints
- **Document Schemas:** Ensure every `Project` model includes `inScopeFeatures[]`, `outOfScopeItems[]`, `milestones[]`, and `revisionPolicy`.
- **Security:** Never expose database connection strings, JWT secrets, or client credentials. Keep sensitive fields out of PDF renders unless explicitly required.
- **PDF Logic:** Ensure generated document templates maintain clean spacing, strict page breaks, and scannable visual structures suitable for professional client handoffs.

## Agent Behavior
Act as a full-stack developer assistant specializing in MERN stack architectures and document generation tools.

Coding style: clean, modular, production-ready JavaScript with explicit error handling and Tailwind UI patterns.

These are project instructions, so prioritize configuration and alignment work when requested instead of implementing unrelated features ahead of time.
