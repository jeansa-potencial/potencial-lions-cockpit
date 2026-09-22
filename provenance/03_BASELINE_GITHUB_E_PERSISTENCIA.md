# Baseline GitHub e Persistência Técnica

## Requirement

All code and material technical documentation for the Potencial & Lions Partnership Cockpit must be persisted in GitHub. GitHub is the durable application-engineering record and must not depend on Cowork transcript history.

## Repository role

GitHub stores:
- application source code;
- Apps Script source and deployment configuration that can safely be versioned;
- frontend source;
- architecture and technical decisions;
- requirements and acceptance criteria;
- security and integration documentation;
- release notes and changelog;
- test plans and test evidence that is appropriate to persist;
- runbooks, recovery instructions and troubleshooting;
- migration notes and technical backlog where material.

GitHub does **not** become the canonical source for live operational task state. That remains in Notion.

## Suggested repository baseline

```text
potencial-lions-cockpit/
├── README.md
├── docs/
│   ├── mission-and-authority.md
│   ├── architecture.md
│   ├── requirements.md
│   ├── business-rules.md
│   ├── notion-data-model.md
│   ├── integration-contract.md
│   ├── security.md
│   ├── ux.md
│   ├── testing.md
│   ├── deployment.md
│   ├── change-protocol.md
│   └── changelog.md
├── apps-script/
├── frontend/
├── tests/
├── releases/
└── .gitignore
```

This structure is a reference, not a business rule. Cowork may improve it while preserving recoverability and the required documentation domains.

## Secret handling

Never commit:
- Notion integration tokens;
- passwords or session secrets;
- private keys;
- Google OAuth secrets;
- production environment secrets;
- personal credentials.

Use server-side secret/configuration storage suitable to the chosen runtime. For Apps Script, Script Properties are an available server-side key/value mechanism for application configuration; production secret handling must be implemented and reviewed accordingly.

## Minimum repository controls

- meaningful README;
- explicit environment/setup instructions;
- main branch representing releasable state;
- recoverable version history;
- release/version naming convention;
- changelog for material behavior changes;
- no plaintext secrets;
- documentation updated in the same technical change when architecture or runtime behavior materially changes.

