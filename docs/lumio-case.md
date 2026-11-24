# Case note: Lumio, a paused personal-awareness assistant

A short case about a project I paused, and what the research behind it showed. It is here because deciding what *not* to build on evidence is part of how I work. Lumio has no public showcase, no screenshots and no user claims.

> **Status: paused.** The source code is private. Last development activity was in April 2026. I have no information about real users, and none are claimed. The project's own name is provisional.

## What it was

A personal life-awareness assistant, built as a web app with Next.js, Supabase and the Claude API. The focus was life rhythm, the gap between intention and behaviour, patterns, and important things that get overlooked. Early versions connected to health data, calendar and email, with the user's consent.

**Hypothesis:** the gap between what people intend and what they do is an under-served angle in the self-tracking and journaling category. I haven't validated this.

## What the research found (sources accessed 30 October 2026)

- **Fitness data source is closing.** New developer sign-ups for the Google Fit API closed in 2024, and the API is documented as supported only until the end of 2026. The migration path is a different platform (Health Connect), which needs an Android app.
- **Email access is expensive to do properly.** Reading Gmail falls under Google's "restricted" scopes. Holding that data on a server requires an annual third-party security assessment, and an unverified app is capped at 100 users.
- **Health data is special-category data.** Under GDPR and Turkish KVKK it needs explicit consent and adequate safeguards. Sending it to servers or model providers abroad needs a transfer mechanism.
- **Conflict with a product principle.** My own principle was to take the lowest legal risk. Storing health records and access tokens on a server contradicts that.

## Decisions and options

The research suggested a much simpler version: a manual daily check-in of one to three questions, a user-defined list of intentions and priorities, and a weekly reflection with at most three observations that states its assumptions. Data would stay on the device.

I treated freezing the email and fitness integrations as the option to evaluate, not as a settled decision. The project is paused while those choices stay open. I haven't tested the simpler version with users.

## Open questions

- Is there real demand for this angle, or is the category's known weakness (low long-term retention) decisive? I couldn't open the primary source for retention figures, so I make no claim about them.
- Which market, and web or mobile?
- What is the legal and security budget?

## What this shows about my approach

- I check platform and regulatory constraints before investing further.
- I let the cost of data handling shape the scope, and I prefer collecting less data over building controls around more.
- I keep decisions I haven't made labelled as open, as in [the other case notes](../README.md).
