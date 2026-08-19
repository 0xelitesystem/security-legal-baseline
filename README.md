# security-legal-baseline

A pre-launch security and legal checklist for solo builders shipping web products. About 250 items covering what to lock down before strangers touch your code or your money.

This is the actual baseline used before shipping. Not a "best practices" article. Not generated. Items earn their place by mapping to a specific failure mode (OWASP A01, GDPR Article 32, broken access control, leaked .env, prompt injection) or a real incident pattern.

## What's inside

One file: `security-legal-baseline.md`. Four sections.

### Security baseline

-> Secrets and credentials
-> Transport and headers
-> Auth and sessions
-> Authorization
-> Input and output
-> Rate limits and abuse
-> Data handling
-> Logging and monitoring
-> Dependencies and supply chain
-> DNS and email infrastructure
-> Backup and recovery
-> AI / LLM specific
-> Pre-launch verification

### Legal and compliance baseline

-> Required pages on every public site (Privacy, Terms, Cookie notice, Refund, DMCA, Affiliate disclosure, Accessibility)
-> Data subject rights (GDPR, CCPA, COPPA)
-> Consent and marketing disclosure (CAN-SPAM, TCPA, FTC endorsement guides, click-to-cancel)
-> Vendor and subprocessor management (DPAs, breach notification)
-> Business protection (entity, EIN, trademark, insurance, sales tax nexus)
-> Industry-specific (HIPAA, GLBA, FERPA, COPPA, PCI-DSS, SOC 2)

### Hard rules

Things you never violate. Plaintext passwords, secrets in frontend bundles, `eval` on user input, auto-filling payment forms, disabling CSRF "temporarily" without a ticket to re-enable.

### Stack-check before adding tools

Before adopting a new security or compliance tool, verify the existing stack does not already solve it. Cloudflare covers WAF, rate limit, DDoS, bot management. Most hosts ship HSTS, TLS, and basic headers out of the box. Stripe handles PCI scope. Most baseline items are configuration, not new purchases.

## How to use

1. Read it once end to end so you know what is in there.
2. Before launch, walk it top to bottom.
3. Quarterly, walk it again on any project with paying users or PII.
4. After any incident, dependency CVE that hits your stack, or material feature change, walk it again.

If a rule is consciously waived, document the waiver and the reason somewhere in the project docs. The list is the floor, not a wish list.

## Why this exists

Most launch checklists online are 20 items long, half of them are marketing fluff ("validate your idea", "talk to users"), and they skip the things that actually take you down. Broken access control. Leaked secrets. Missing rate limits. No DMARC. No privacy policy. No DPA with the LLM vendor that just got served a subpoena. This assumes you already validated and you are trying not to get pwned, fined, or sued.

## Scope and limits

This is a baseline. Not legal advice. Not a security audit. Not a substitute for hiring a lawyer or a penetration tester when you have real revenue or real PII at scale. It is the floor a single builder can hold without a security team.

Jurisdictions mentioned are mostly US plus GDPR/UK because that is the lane most indie SaaS ships into. If you sell into other regions, add the local equivalents. If you build in regulated industries (health, finance, education), the industry-specific section points to the regimes that override everything else in here.

## More

Part of a catalog of single-file browser tools and plain-language references, all MIT licensed and dependency-free: [0xelitesystem.github.io](https://0xelitesystem.github.io/). Built by [elitesystem.ai](https://elitesystem.ai).

## License

MIT.

## Related

- [solo-saas-launch-checklist](https://github.com/0xelitesystem/solo-saas-launch-checklist) lighter pre-launch checklist, broader scope (security, legal, SEO, UX, launch)
- [byok-security-checklist](https://github.com/0xelitesystem/byok-security-checklist) threat model for "Bring Your Own Key" products
- [legal-pages-starter](https://github.com/0xelitesystem/legal-pages-starter) Terms, Privacy, Disclaimer HTML templates with fill-in-the-blanks
- [ai-product-disclaimers](https://github.com/0xelitesystem/ai-product-disclaimers) copy-paste disclaimers for AI-powered features
- [csp-builder](https://github.com/0xelitesystem/csp-builder) build Content-Security-Policy headers without the footguns
- [wcag-audit-snippet](https://github.com/0xelitesystem/wcag-audit-snippet) accessibility check bookmarklet
