# SAHORA Technologies — Final Website Project

A Next.js + TypeScript website project using the supplied SAHORA Technologies logo, a black/gold/white visual system, and English/Sinhala/Tamil content. Includes public page templates, a dashboard visual preview, a proposed Supabase schema, and deployment notes.

## Important implementation status

This project is a **website source starter / front-end build**, not a deployed production service. The public pages and localized copy are implemented. The admin area is intentionally labelled as a preview. The secure production authentication flow, dashboard CRUD, database-backed content loading, and enquiry persistence are not yet connected. The enquiry API fails closed with HTTP 503 until a secure backend is implemented; this prevents the form from silently pretending to work.

Do not advertise the admin dashboard or contact form as operational until the remaining integration and testing are completed.

## Included

- Next.js App Router and TypeScript project
- English (`/en`), Sinhala (`/si`), and Tamil (`/ta`) website content
- Home, About, Services, Process, Projects, Contact, FAQs, Insights, Privacy, Terms, Cookies
- Responsive black, metallic-gold, and white styling
- Supplied brand logo in `public/images`
- Dashboard and sign-in page visual previews
- Supabase schema with translations, services, projects, posts, FAQs, enquiries, profiles, media, settings, audit logs, and RLS starter policies
- `.env.example` and deployment guidance

## Run locally

Requirements: Node.js 20 LTS recommended.

```bash
npm install
cp .env.example .env.local
npm run dev
```

Open `http://localhost:3000`. The root route redirects to `/en`.

Supabase environment values can remain unset while viewing the public pages; backend operations are not active until implemented.

## Configure Supabase

1. Create a Supabase project.
2. Review `supabase/schema.sql` and run it against a fresh project after verifying the policies fit your intended roles.
3. Set `NEXT_PUBLIC_SUPABASE_URL` and `NEXT_PUBLIC_SUPABASE_ANON_KEY`.
4. Implement server-side session validation and authorization before enabling admin data operations.
5. Create the first administrator securely through the Supabase dashboard and provision their `profiles` row using a trusted process.
6. Test RLS as anonymous, staff, editor, sales, and admin roles.
7. Implement server-side enquiry validation, rate limiting, spam protection, persistence, and email notifications. Do not add a public insert policy that exposes unrestricted writes.
8. Implement CRUD forms for the dashboard modules. The current admin screens are only visual previews.

Never put a Supabase service-role key in client code, public environment variables, or the repository.

## Deploy on Netlify

1. Push this project to a private or public GitHub repository.
2. In Netlify, import the repository as a new site.
3. Use the Next.js framework preset / detected Next.js build settings. Confirm support for the selected Next.js runtime and features under the current plan.
4. Add the environment variables in Netlify site settings.
5. Deploy to a preview URL and test all three languages, mobile navigation, SEO metadata, and route behaviour.
6. Finish backend integration and run the production security checklist before enabling launch.
7. Connect a purchased domain and verify HTTPS, canonical URLs, redirects, and sitemap handling.

Netlify and Supabase accounts, domain registration, email delivery, backups, and usage beyond provider free tiers may incur charges.

## Before public launch

- Replace placeholder email/phone details with official business contact information.
- Review company copy, mission/vision, services, and all Sinhala/Tamil translations.
- Finalize legal policy wording based on actual data practices and applicable law.
- Complete admin authentication, role permissions, dashboard CRUD, and database integration.
- Complete contact-form persistence, spam prevention, email notifications, and success/error states.
- Add a sitemap, robots.txt, Open Graph assets, favicon, and structured data appropriate to the final domain.
- Verify keyboard accessibility, contrast, image alt text, performance, backups, restoration, and security.
- Do not publish invented testimonials, project results, addresses, or contact details.

## Brand details

Primary palette: near-black `#080808`, metallic gold `#E9B949`, white `#F5F3ED`, muted text `#A7A399`.
Tagline: **IDEAS › CODE › IMPACT**.
