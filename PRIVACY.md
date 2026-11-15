# Privacy Policy

**Last Updated: November 15, 2026**

This Privacy Policy describes how "PMBot for Jira" (the "Application") collects,
uses, and stores information when you install and use it within your Atlassian
Jira instance.

## 1. Data Minimization

PMBot is built around a data minimization principle. It bridges Jira and
Telegram to deliver notifications and enable status transitions, without
collecting personal identifiable information (PII) beyond what is strictly
required for routing messages.

## 2. What We Collect and Where It Is Stored

### 2.1 Stored in Your Jira Instance (Atlassian Forge)

Within the secure infrastructure of your own Atlassian environment, the
Application stores:

- Jira user identifiers (Atlassian Account IDs).
- Project configuration (reporting schedules, workflow phase order, and
  assigned roles such as Project Leader).
- Local mapping between Jira users and their linked Telegram bot connection.

### 2.2 Processed by the Central Router (Google Cloud Platform)

To allow a single Telegram account to connect to multiple Jira instances, a
central router hosted on Google Cloud Platform (GCP) stores only the following
technical data:

- Your public numerical Telegram identifier (Chat ID).
- An array of webhook URLs for the Jira instances you have authorized.
- Single-use temporary tokens for account registration, which self-destruct
  after 24 hours or upon use.

### 2.3 What We Do Not Collect

PMBot does not collect, process, or store usernames, email addresses,
physical locations, or job titles. The developer of the Application has no
access to your Jira tickets, comment history, user credentials, or Telegram
conversations.

## 3. Message Content in Transit

Task titles, descriptions, progress comments, and assignee names travel in
encrypted form between Jira, the GCP proxy, and Telegram. The proxy acts
exclusively as a real-time conduit: GCP does not log, store, or retain the
content of your messages or ticket data.

## 4. Data Retention and Deletion

- Uninstalling the Application from "Manage Apps" in your Jira instance
  immediately stops notifications from that project and removes the data
  stored in your Forge instance.
- To remove your digital footprint from the central router, you may request
  deletion of your Telegram Chat ID, or simply block and delete the
  conversation with the bot in Telegram, which invalidates any future
  routing attempts.

## 5. Third-Party Sub-processors

The Application relies on the following infrastructure providers, each
governed by their own privacy and security practices:

- **Atlassian Forge** — hosts app data within your Jira tenant.
- **Google Cloud Platform** — hosts the central routing proxy.
- **Telegram** — delivers and receives messages on behalf of the user.

## 6. Contact

Questions about this Privacy Policy can be directed to
**contact@pmbotforjira.com**.
