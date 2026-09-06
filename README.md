# Andromeda Docs

Artifact-only GitHub Pages deployment repository for
[andromeda-docs.greybodygames.com](https://andromeda-docs.greybodygames.com/).

The authoritative Fumadocs application, project documentation, generated-reference tooling, and Unreal
C++ source are maintained privately in the Andromeda source repository. This repository stores neither
application source nor generated site output.

## Deployment

The private Andromeda repository validates and builds the documentation once, uploads
`site-andromeda-docs` as an immutable workflow artifact, and dispatches this repository's deployment
workflow with the exact source workflow run ID.

The destination workflow downloads that fixed artifact, validates it, repackages it as a GitHub Pages
artifact, and deploys it without checking out this repository, installing dependencies, rebuilding
Fumadocs, committing, or pushing.

A manual deployment requires the source Andromeda workflow run ID. The corresponding source artifact
must still be within its retention period.

The custom domain is configured in this repository's GitHub Pages settings. A `CNAME` file and deployment
branch are not used.

## Licensing

- The workflow and repository documentation are available under the [MIT License](LICENSE-CODE.md).
- The deployed application, documentation content, generated reference, media, and asset rights remain
  governed by their respective sources and are not licensed by this deployment repository.
