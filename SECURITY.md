# Security

**Last Updated: November 15, 2026**

This page describes the security practices of "PMBot for Jira" (the
"Application").

## 1. Architecture

PMBot uses a split architecture to minimize data exposure:

- **Atlassian Forge** hosts the app's logic and stores configuration and user
  mapping data inside your own Jira tenant, under Atlassian's security model.
- **Google Cloud Platform (GCP)** hosts a lightweight routing proxy that
  allows a single Telegram account to connect to multiple Jira instances. It
  stores only a Telegram Chat ID, authorized webhook URLs, and short-lived
  registration tokens (24-hour expiry).
- **No ticket content** (titles, descriptions, comments) is stored by the
  proxy. It is relayed in transit only.

## 2. Encryption

- All communication between Jira, the GCP proxy, and Telegram uses
  HTTPS/TLS in transit.
- Data at rest in Atlassian Forge storage and in GCP follows the respective
  platforms' built-in encryption-at-rest standards.

## 3. Access Controls

- The Application requests the minimum set of Jira API scopes required for
  its functionality.
- Requests made on behalf of a user use `asUser()` authorization, which
  enforces the user's own Jira permissions.
- Access to the Strategic Dashboard and administrative configuration is
  restricted to users who are Jira Project Administrators or who have been
  explicitly designated as a Leader within PMBot's admin panel.

## 4. Secrets Management

- API tokens, bot credentials, and signing secrets are stored as environment
  variables / managed secrets within Forge and GCP, and are never committed
  to source control or exposed to the client.

## 5. Vulnerability Management

- Dependencies are tracked and updated regularly using automated tooling
  (e.g., `npm audit` / Dependabot alerts).
- Security patches are prioritized according to severity and applied as
  soon as practical.

## 6. Reporting a Vulnerability

If you discover a security issue, please report it to
**contact@pmbotforjira.com**. We aim to acknowledge reports within 2
business days and will work with you to understand and address the issue
promptly. Please avoid publicly disclosing a vulnerability until it has been
resolved.

## 7. Incident Response

In the event of a confirmed data security incident affecting customer data,
affected administrators will be notified without undue delay, along with a
description of the impact and remediation steps taken.

## 8. Platform Certifications

PMBot does not independently hold SOC 2 or ISO 27001 certifications. It
runs entirely on infrastructure that does:

- Atlassian Forge operates under Atlassian's own security and compliance
  program.
- Google Cloud Platform is independently certified under ISO 27001, SOC 2,
  and other industry standards.

## 9. Contact

For any security-related question or report, contact
**contact@pmbotforjira.com**.
