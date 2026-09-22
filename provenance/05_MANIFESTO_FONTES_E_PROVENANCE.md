# Manifesto de Fontes e Provenance

## Human Authority baseline

The following items are approved mission constraints for this package:
- institutional identity: **Potencial & Lions**;
- Jean and Marina may remain individual accountability actors, but the partnership/application identity is Potencial & Lions;
- Business/Operations development continues in the ChatGPT track;
- Claude/Cowork owns Application Engineering and Jean participates directly there;
- business rules require Jean's approval;
- no administrative inter-AI messaging loop;
- communication between tracks occurs only on material boundary changes;
- GitHub is mandatory for persistent technical documentation and application source;
- Notion is the intended canonical operational backend;
- Google Apps Script is the selected permanent runtime/bridge/host baseline unless a later authorized technical decision changes that architecture;
- a Sprint may contain several uninterrupted internal phases without microapproval.

## Existing prototype

Reference artifact included in this package:
- `reference/Cockpit_Potencial_Lions_Sprint1_AtualAte20260921_v1-1.html`
- purpose: approved starting UX/product prototype, not production security or production persistence.

## Official external references used in this package

### Anthropic / Claude Cowork
- Anthropic, **Cowork Workshop: Foundations** — Cowork supports delegated multi-step work, working folders, connected tools, browser/web-app context, global instructions, projects, skills and plugins.  
  https://www.anthropic.com/webinars/cowork-workshop-foundations
- Anthropic Engineering, **How we contain Claude across products** — Cowork runs in a contained local VM with the selected workspace folder mounted, relevant to understanding execution boundaries.  
  https://www.anthropic.com/engineering/how-we-contain-claude
- Anthropic, **Introducing Agent Skills** — Skills are folders containing instructions, scripts and resources and are composable across Claude surfaces.  
  https://www.anthropic.com/research/skills

### Google Apps Script
- Google for Developers, **Web Apps** — Apps Script can publish browser-accessible web apps using `doGet(e)` / `doPost(e)` and deployment settings.  
  https://developers.google.com/apps-script/guides/web
- Google for Developers, **Properties Service** — Apps Script provides Script/User/Document property stores for application configuration and preferences.  
  https://developers.google.com/apps-script/guides/properties

### GitHub
- GitHub Docs, **About repositories** — repositories store code, files and revision history.  
  https://docs.github.com/en/repositories/creating-and-managing-repositories/about-repositories
- GitHub Docs, **About Git** — version control tracks change history and permits recovery of earlier versions.  
  https://docs.github.com/en/get-started/using-git/about-git
- GitHub Docs, **Best practices for repositories** — recommends README and repository security practices.  
  https://docs.github.com/en/repositories/creating-and-managing-repositories/best-practices-for-repositories

### Notion
- Notion Developers, API reference; current API examples use bearer-token authentication and current versioned endpoints.  
  https://developers.notion.com/reference/intro
  https://developers.notion.com/reference/create-view

## Provenance policy

- Human Authority decisions govern business rules and mission boundaries.
- Official platform documentation governs mutable platform mechanics.
- Architecture recommendations in the technical report are implementation baselines, not business facts.
- The supplied prototype is evidence of intended UX direction, not evidence that production integration/security has already been implemented.

