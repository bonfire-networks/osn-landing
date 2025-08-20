---
layout: main/base.html
title: Open Science Network
description: Reclaim scientific discourse with federated digital spaces where researchers shape their own conversations, data, and collaborations, participating in the open social web on their terms.
---

<div class="prose mx-auto my-16 max-w-3xl">

# Open Science Network Configuration Guide

This guide covers how to configure and deploy your own Open Science Network instance (powered by Bonfire).


<div role="alert" class="alert mt-6 max-w-3xl mx-auto items-start alert-info">
    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" class="h-6 w-6 shrink-0 stroke-current"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
    <div class="flex text-base flex-col">
        <span class="font-bold">Want professional deployment support?</span>
        <div>Join our <a href="/pilots">pilot program</a> for complete implementation assistance and researcher training, or <a href="https://cal.com/bonfire-networks/meet" target="_blank">book a call to discuss managed hosting</a> for hands-off deployment.</div>
    </div>
</div>

## Prerequisites

- Deploy an instance using the [Bonfire deployment guide](https://docs.bonfirenetworks.org/deploy.html), setting `open_science` as the flavour.

## Environment Configuration

### ORCID Application Setup

1. **Register your application** at [ORCID Developer Tools](https://orcid.org/developer-tools) (or [Sandbox](https://sandbox.orcid.org/developer-tools) for testing)
2. **Set redirect URIs** for your instance in the ORCID app setup:
   ```
   https://your-domain.org/settings/orcid/callback
   ```
3. **Copy credentials** to your Bonfire environment or `.env` file (see example below)
<!-- 4. **Set application permissions** to read public information and publication lists -->
4. **Restart** Bonfire

### Zenodo Application Setup (Optional)

1. **Create application** at [Zenodo Developers](https://zenodo.org/account/settings/applications/) (or [Sandbox](https://sandbox.zenodo.org/account/settings/applications/) for testing)
2. **Set redirect URIs** for your instance in the Zenodo app setup:
   ```
   https://your-domain.org/settings/zenodo/callback
   ```
3. **Copy credentials** to your Bonfire environment or `.env` file (see example below)
4. **Restart** Bonfire

---

### OSN Environment Variables

Add these variables to your Bonfire environment or `.env` file:

```bash
FLAVOUR=open_science # sets Bonfire flavour

# ORCID Integration (Required)
# ORCID_ENV=sandbox # uncomment if using the sandbox API
ORCID_CLIENT_ID=your_orcid_client_id
ORCID_CLIENT_SECRET=your_orcid_client_secret
# ORCID_WITH_MEMBER_API=yes # uncomment only if your organisation (used to create these API keys) is an ORCID member

# Zenodo Integration (Optional - for archiving discussions)
# ZENODO_ENV=sandbox # uncomment if using the sandbox API
ZENODO_CLIENT_ID=your_zenodo_client_id
ZENODO_CLIENT_SECRET=your_zenodo_client_secret
```

---

### Support Resources
- [Bonfire Technical Chat](https://matrix.to/#/#bonfire-tech:matrix.org)
- [ORCID Developer Documentation](https://info.orcid.org/documentation/)
- [Zenodo API Documentation](https://developers.zenodo.org/)

</div>