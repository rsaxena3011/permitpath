# PermitPath

**Stage: IDEA. Nothing is built yet.** This repository holds the concept and
application record for PermitPath, prepared for the Startup Buildathon India
2026. There is no product, no code, no company, no customers and no revenue —
and this README claims none. Everything product-shaped below is a plan,
written in future tense.

## The problem

Live events in India run on permissions, and the requirements are
city-specific: they change with the city, the venue, the crowd size, amplified
sound, food and alcohol service, drones, fireworks and temporary structures.
There is no single place where an organiser can see, for their exact event,
what they will need. Organisers discover requirements late — through venue
managers, local agents and word of mouth — and a single missing approval (a
police permission, a fire NOC, a local-body licence) can delay an event or
cancel it outright, after the money is spent.

## The planned product

PermitPath is planned as an AI event-permit and venue-readiness copilot. The
organiser will enter their city and venue, event type and date, expected
audience, and the features of their event (sound, food, alcohol, drones,
fireworks, structures, indoor or outdoor). PermitPath will return one
readiness checklist: the likely required permissions, the documents each one
needs, the responsible authority, a deadline for each step, and a readiness
score from 0–100 with the gaps flagged.

First scope, if built: Mumbai only, three event types — corporate events,
weddings and product launches. First customers would be corporate event
agencies, wedding planners, venues and hotels, independent organisers and
production companies.

**Boundary, stated plainly:** PermitPath will not issue permits, will not
file applications, and is not legal advice. Official portals are where
applications get filed; PermitPath is planned to sit before them, in the
preparation stage — where the confusion, the missing documents and the lost
days actually are.

## Trust design (planned)

Because this is regulatory information, the product will be designed so it
cannot silently invent a rule:

- **Source-first:** every requirement carries a link to its source, or is
  explicitly marked unverified.
- **Confidence labels:** each item labelled Confirmed, Likely, or Needs
  verification.
- **Date stamps:** every source shows when it was last checked.
- **Human confirmation:** the organiser reviews and confirms the final
  checklist before it is shared or acted on.

## Planned architecture (nothing below exists yet)

- **Intake:** a web app will collect the event profile and uploaded venue
  documents; documents in Cloud Storage, event state in Firestore.
- **Document understanding:** Gemini will read uploaded documents and extract
  the facts that drive requirements.
- **Grounded retrieval:** requirements will be retrieved against official
  sources using Gemini with grounding / Vertex AI Search, so each item is
  tied to a citable source.
- **Structured output:** Gemini structured output / function calling will
  convert retrieved requirements into the fixed checklist schema: permission,
  documents, authority, deadline, confidence label, source, last-checked date.
- **Venue context:** the Google Maps Platform will confirm the venue's
  location and local jurisdiction.
- **Reports:** the confirmed checklist will be rendered into a shareable
  report through the Google Docs API / PDF export.
- **Serving:** Cloud Run. Prototyping will start in Google AI Studio against
  the Gemini API.

## Founder

Ratnesh Saxena — solo founder, Mumbai. Head of Video Production at Eclat
Media Worldwide, a corporate-events agency (his employer, not this venture),
with 10+ years in video production, motion design, editing and visual
storytelling; he leads a five-person production team and builds software
solo. PermitPath comes from the world he works in every day: corporate
events, where venues, vendors, staging, sound and production timelines have
to come together on a fixed date.

- LinkedIn: https://www.linkedin.com/in/ratnesh-saxena-01a6a288

## Status and next steps (planned, not done)

- Venture stage: idea stage, unincorporated, bootstrapped. No external
  funding has been raised.
- Next steps, in order: validate the preparation gap with Mumbai organisers;
  build the Mumbai-only prototype for the three event types; assemble the
  first sourced requirement library.

## Licence

MIT — see `LICENSE`.
