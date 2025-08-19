---
layout: main/base.html
title: Open Science Network
description: Reclaim scientific discourse with federated digital spaces where researchers shape their own conversations, data, and collaborations, participating in the open social web on their terms.
---

<div class="prose mx-auto my-16 max-w-3xl">

# Open Science Network User Guide

## Open Science Network Features

### 1. Sign In with ORCID

**What it does:** Enables researchers to authenticate with ORCID, automatically importing their professional profile and publication history.

**User experience:**
- "Sign in with ORCID" option on the login page
- One-click authentication via ORCID
- Profile auto-populated with verified academic identity
- Publications imported from ORCID record
- Optionally, can also link ORCID in your profile settings after signing up

**Requirements:** [ORCID API configuration](/setup)

### 2. Archive Discussions on Zenodo

**What it does:** Integrates with Zenodo to preserve academic discussions as FAIR digital objects with DOIs.

**Process:**
1. Connect your Zenodo account during login or in user settings  
2. Moderators or post authors can archive discussions
3. Metadata is formatted according to FAIR principles
4. Content is deposited to Zenodo with a persistent DOI
5. Archived discussions become citable and are linked within the thread
6. Complete provenance chain maintained

**Metadata includes:**
- Participants and ORCID IDs
- Upload type
- Timestamps and context
- Access rights
- Keywords
- Licensing information

**User experience:**
- Connect Zenodo account on login or in settings
- On a discussion, click the 3-dot icon below the main post. If you are the author, you'll see "Archive with Zenodo"
- Fill in the modal to archive the full discussion (including co-authors) or just the main post
- Creates DOIs for preserved conversations

**Requirements:** [Zenodo API configuration](/setup)

### 3. Profile Widgets Configuration

**What it does:** Customizable widgets display research-specific info on user profiles.

Go to your settings and click *Open Science* under extensions. Toggle which widgets appear on your profile and others'.

**Available widgets:**
- **Affiliations Widget**: Show institutional affiliations from ORCID
- **Author Info Widget**: Show stats like works count, citations, h-index from OpenAlex
- **Author Topics Widget**: Show research topics from OpenAlex
- **Publication Types Widget**: Show breakdown by publication type from OpenAlex
- **Recent Publication Widget**: Show your most recent work from OpenAlex

### 4. Research Feed

**What it does:** Custom feed aggregating publication activity across the federated network.

Go to settings and click *Feed presets*. Add the "Research" feed to your sidebar.

**Features:**
- Publication shares with rich metadata previews
- Cross-institutional research updates
- Repository integration for new datasets and papers
- Filtered for academic discourse
- Discovery tools for finding research and collaborators

### 5. Publication Preview

**What it does:** Generates rich previews when publications are shared in posts.

**Features:**
- Automatic metadata extraction from DOIs and repository links
- Co-author identification and tagging
- Citation info display
- Open access link detection
- Related publication suggestions

---

### Support Resources
- [Bonfire Community Chat](https://matrix.to/#/#bonfire-networks:matrix.org)

</div>