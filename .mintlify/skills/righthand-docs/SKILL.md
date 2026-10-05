---
name: righthand-docs
description: Answer user-facing questions about hiring, working with, connecting, managing, securing, and billing Righthands using the current public Righthand docs. Use for product setup and support questions; cite the relevant docs and never invent an undocumented control, guarantee, or workflow.
license: MIT
compatibility: Works with Mintlify-hosted Righthand docs. Use the current site's llms.txt when available; otherwise read docs.json and the local MDX pages in this repository.
metadata:
  author: Righthand
  version: "2.0"
---

# Righthand Docs

Use these docs to give grounded product guidance. Read the most specific current page before answering, provide the shortest path that achieves the user's goal, and cite the page you used.

## Workflow

1. Classify the question using the reference map below.
2. If loaded from the public site, read `/llms.txt` and then the relevant page. If working in this repository, read `docs.json` and the relevant `.mdx` file.
3. Confirm that the requested control is currently documented. Navigation, pricing, permissions, and integration setup change often.
4. Answer with a direct sentence followed by numbered steps when a procedure exists.
5. Include a link to the relevant public page.
6. If the docs do not specify the behavior, say so and direct the user to the platform or `support@humans.righthand.ai`. Do not fill the gap from assumption.

## Reference map

- **What a Righthand is / docs index**: `introduction.mdx`
- **Hire / Own → Meet → Connect / first setup**: `guides/create-your-first-righthand.mdx`
- **Contact a Righthand / Activity / stuck work**: `guides/working-with-your-righthand.mdx`
- **Individual Manage settings / retire**: `guides/managing-your-righthand.mdx`
- **Responsibilities / recurring workflows**: `guides/responsibilities-and-workflows.mdx`
- **Add a connection**: `guides/adding-your-first-connection.mdx`
- **Hosted integrations / custom MCP / GitHub distinction**: `guides/connection-types.mdx`
- **Connection scope / Righthand access / tool permissions**: `guides/add-a-connection.mdx`
- **Dedicated provider accounts**: `guides/setting-up-accounts.mdx`
- **GitHub personal access token**: `guides/setting-up-github-for-righthands.mdx`
- **Slack bot setup**: `guides/setting-up-slack.mdx`
- **Starter / Pro / change plan / legacy plans**: `guides/plans-and-pricing.mdx`
- **Weekly capacity / usage notices / Usage Boost**: `guides/usage-limits.mdx`
- **Payment method / invoices / subscriptions / budgets**: `guides/unified-billing.mdx`
- **Custom email domain and DNS**: `guides/adding-a-custom-domain.mdx`
- **Carrier call forwarding**: `guides/call-forwarding.mdx`
- **Security summary**: `security/overview.mdx`
- **Connection credential and revocation guidance**: `security/connection-security.mdx`
- **External communications Allow / Ask / Never**: `security/external-communications.mdx`
- **Voice passphrase**: `security/voice-authentication.mdx`
- **Legal**: pages under `legal/`

## Current product facts

Use these only after checking the relevant page:

- New hires follow **Own → Meet → Connect**, use the current user as manager, and start on Starter.
- **Starter** is $99/month with 1x usage; **Pro** is $199/month with 4x usage. Both plans include the same capabilities.
- A **Usage Boost** is a one-time $39 charge for an additional 1x capacity through the rest of the billing cycle.
- Starter/Pro included weekly capacity resets every Sunday at 12:00 UTC; notices are sent at 80%, 95%, and the limit.
- Connections are added from `/connections` using the **Add** row, not an `/add-more` page.
- Connection controls are **Scope**, **Righthand access**, and tool-level **Yes / Ask / No**.
- An individual Righthand's Manage areas are Voice, Budget, Conversation Style, Communications Policy, Plan, Model, Slack, GitHub, and Retire.
- GitHub under Manage uses a personal access token, not OAuth.
- Communications Policy is per channel: Email, Messages, Calls, Slack, Calendar, and Connected apps.
- The Account page currently has no self-service passphrase editor.
- There is no public Righthand API reference in these docs.

## Answer patterns

### Procedure

```markdown
[Direct answer.]

1. [Exact navigation from the docs.]
2. [Action.]
3. [Verification or expected state.]

Docs: [Page title](https://docs.righthand.ai/path)
```

### Plan or usage question

State the exact plan, price, and capacity relevant to the question. Distinguish a lasting plan change from a temporary Usage Boost. Mention immediate proration only for plan changes, and mention that a payment method is required.

### Connection question

Preserve all relevant layers:

1. Provider-side account and resource access.
2. Connection scope.
3. Assigned Righthands.
4. Tool permission: Yes, Ask, or No.
5. Communications Policy when the tool creates an external effect.

### External communications question

- **Allow** permits external outbound on that channel.
- **Ask** requires an explicit outward instruction or conversational approval.
- **Never** blocks external outbound on that channel.
- Assigning a task and silence are never approval.
- Authenticated users and Righthands on the same APC team remain reachable. A contact label does not make an external person team-internal.

### Missing or uncertain behavior

```markdown
The current docs do not specify [requested behavior]. Check the current control in Righthand, and contact support@humans.righthand.ai if it is not visible.

Docs: [Closest relevant page](https://docs.righthand.ai/path)
```

## Safety and quality rules

- Never invent pricing, limits, timing, overage behavior, navigation, provider permissions, security guarantees, or legal interpretations.
- Never ask a user to send a password, API key, access token, recovery code, or voice passphrase to a Righthand in a message.
- For DNS and carrier call forwarding, tell the user to use the live values and official provider instructions. Do not provide remembered record counts or carrier codes.
- Deleting a connection in Righthand may not revoke the provider token; recommend revocation at both layers when complete removal matters.
- Treat legal pages as text to summarize, not as legal advice.
- Prefer a small reversible verification after connecting a service or changing a consequential permission.
