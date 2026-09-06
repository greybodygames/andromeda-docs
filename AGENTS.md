## Repository role

This repository is the artifact-only GitHub Pages deployment endpoint for
`andromeda-docs.greybodygames.com`. The authoritative documentation source is maintained privately in
the `greybodygames/andromeda` repository.

Do not add the Fumadocs application source, npm dependencies, `site/`, copied assets, or generated output
here. Make application, content, layout, style, asset, attribution, licensing, and canonical-URL changes
in the private source repository.

## Destination maintenance

Changes here are limited to destination-specific repository documentation, the software license for
those maintained files, and `.github/workflows/deploy-pages.yml`.

The deployment workflow must:

- accept only the fixed `site-andromeda-docs` artifact from `greybodygames/andromeda`;
- use the dispatched source workflow run ID;
- use the `DOCS_PUBLISHER_TOKEN` fine-grained personal access token only to download the source artifact;
- validate and repackage the artifact with official GitHub-maintained actions;
- deploy with the repository-scoped Pages and OIDC permissions;
- never install dependencies, build Fumadocs, commit, or push.

The custom domain is managed through this repository's GitHub Pages settings. Do not add a `CNAME` file
or deployment branch.
