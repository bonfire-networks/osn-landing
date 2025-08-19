---
layout: main/base.html
title: Open Science Network
description: Reclaim scientific discourse with federated digital spaces where researchers control their conversations, data and collaborations
---


<div class="prose mx-auto my-16 max-w-3xl">

# Open Science Network Configuration Guide

This guide covers the specific configuration and features for deploying the Bonfire Open Science Network flavour. 
Read it alongside the [official Bonfire deployment guide](https://docs.bonfirenetworks.org/deploy.html).

## Prerequisites

- Everything needed from the [Bonfire deployment guide](https://docs.bonfirenetworks.org/deploy.html)
- ORCID application credentials
- Zenodo application credentials

## Environment Configuration

### Required OSN Environment Variables

Add these variables to your `.env` file:

```bash
# ORCID Integration (Required)
ORCID_CLIENT_ID=your_orcid_client_id
ORCID_CLIENT_SECRET=your_orcid_client_secret

# Zenodo Integration (Optional - for archiving discussions)
ZENODO_ENV=sandbox  # Use 'production' for live deployment
ZENODO_CLIENT_ID=your_zenodo_client_id
ZENODO_CLIENT_SECRET=your_zenodo_client_secret
```

### ORCID Application Setup

1. **Register your application** at [ORCID Developer Tools](https://orcid.org/developer-tools)
2. **Configure redirect URIs** to whitelist your instance:
   ```
   https://your-domain.org/settings/orcid/callback
   ```
3. **Copy credentials** to your `.env` file
4. **Set application permissions** to read public information and publication lists

### Zenodo Application Setup (Optional)

1. **Create application** at [Zenodo Developers](https://zenodo.org/account/settings/applications/) (or [Sandbox](https://sandbox.zenodo.org/account/settings/applications/) for testing)
2. **Configure redirect URI**:
   ```
   https://your-domain.org/settings/zenodo/callback
   ```
3. **Copy credentials** to your `.env` file

---

## Open Science Network Features

### 1. Sign In with ORCID

**What it does:** Allows researchers to authenticate using their ORCID credentials, automatically importing their professional profile and publication history.

**User experience:**
- Users see "Sign in with ORCID" option on login page
- One-click authentication through ORCID
- Automatic profile population with verified academic identity
- Publications automatically imported from ORCID record
- Alternatively, users can link their ORCID account in the edit profile page after login

**Requirements:** `ORCID_CLIENT_ID` and `ORCID_CLIENT_SECRET` configured

### 2. Archive Discussions on Zenodo

**What it does:** Enables integration with Zenodo for preserving valuable academic discussions as FAIR digital objects with DOIs.

**Process:**
1. Connect your Zenodo account during login or in user settings  
2. Community moderators or post authors can archive discussions
3. Discussion metadata is formatted according to FAIR principles
4. Content is deposited to Zenodo with persistent DOI
5. Archived discussions become citable scholarly objects and are linked within the Thread itself
6. Complete provenance chain maintained

**Generated metadata:**
- Participants and their ORCID IDs
- Upload type
- Discussion timestamps and context
- Access right
- Keywords
- Licensing information

**User experience:**
- Connect your Zenodo account on login or in user settings
- On the discussion page, click the 3-dot icon below the main post. If you are the post author, you will see the "Archive with Zenodo" button.
- Fill in the required fields in the modal to archive either the full discussion or only the main post, including other participants as co-authors
- Creates DOIs for preserved conversations

**Requirements:** `ZENODO_CLIENT_ID` and `ZENODO_CLIENT_SECRET` configured

### 3. Profile Widgets Configuration

**What it does:** Customizable widgets display research-specific information on user profiles.

Navigate to your settings and click the *Open Science* link below the extensions section. You will see a list of toggleable options that determine what appears when viewing your profile and other scientists' profiles.

**Available widgets:**
- **Affiliations Widget**: Display your institutional affiliations from ORCID on your profile page

- **Author Info Widget**: Display author statistics like works count, citations, and h-index from OpenAlex

- **Author Topics Widget**: Display research topics associated with your publications from OpenAlex
 
- **Publication Types Widget**: Display a breakdown of your publications by type (articles, books, etc.) from OpenAlex

- **Recent Publication Widget**: Display your most recently published work from OpenAlex

### 4. Research Feed

**What it does:** Custom feed aggregating publication activities across the federated network.

Navigate to your settings and click the *Feed presets* link. Add the "Research" custom feed to your sidebar.

**Features:**
- **Publication shares** with rich metadata previews
- **Cross-institutional** research updates
- **Repository integration** showing new datasets and papers
- **Filtered content** focused on academic discourse
- **Discovery tools** for finding relevant research and collaborators


### 5. Publication Preview

**What it does:** Generates rich previews when publications are shared in posts.

**Features:**
- **Automatic metadata extraction** from DOIs and repository links
- **Co-author identification** and tagging
- **Citation information** display
- **Open access link detection**
- **Related publication suggestions**

---

### Support Resources
- [Bonfire Community Chat](https://matrix.to/#/#bonfire-networks:matrix.org)
- [ORCID Developer Documentation](https://info.orcid.org/documentation/)
- [Zenodo API Documentation](https://developers.zenodo.org/)


</div>