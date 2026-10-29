Trueman Baldwin

Computer science student at the College of Charleston (B.A., May 2027). I mostly build web apps in TypeScript on PostgreSQL, and right now I'm sharpening my Python, Java and Linux.

Looking for software engineering internships and new-grad roles.

What I've built (these repos are private; I'm happy to walk through any of them)

farmsie: an online marketplace for local farms · farmsie.app

Farms quote each order before the buyer confirms, with recurring orders, a map view and in-app messaging. It runs on a 24-table PostgreSQL database.
Prevents overselling when two people check out at once: a conditional stock update rolls back the losing order, and a CI test runs two purchases at once against a real database.
Held payments with Stripe Connect. The buyer is charged at checkout, and the money goes to the farm on hand-off or back to the buyer on cancellation, with safeguards against duplicate or conflicting payment actions.
LeadVault: an AI phone receptionist for contractors · leadvault.baldwinseo.com

Answers a family contracting business's missed calls, on Twilio and Vapi. Since June 2026 it has handled 149 non-spam calls lasting at least 15 seconds, 34 of them after hours.
Turns each call transcript into a lead card with the Anthropic API, validating the response and flagging failures for review.
Client portal: each business sees only its own data

PostgreSQL row-level security, checked in CI by querying each table as two separate accounts.
Websites: HTML, CSS and JavaScript

For a Charleston pressure-washing company and a family contracting business, each with service pages and an online quote form.
(Public code, Stack and Contact sections follow, toned down the same way.)
