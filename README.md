# LeftLevel

Public website source for [LeftLevel.org](https://leftlevel.org).

LeftLevel is a privacy-first communication initiative focused on resilient, user-controlled conversations, clear security boundaries, and practical architecture that can be reviewed before it is trusted.

## What this repository contains

This repository contains the public static website for LeftLevel.org, including:

* Website pages
* Public documentation entry points
* Brand and visual assets used by the website
* Search engine files such as `robots.txt` and `sitemap.xml`
* Deployment workflow for publishing the static site to DreamHost

The website is intentionally static so it is easier to inspect, deploy, secure, and maintain.

## Project links

* Website: https://leftlevel.org
* GitHub organization: https://github.com/LeftLevelOrg
* Website source: https://github.com/LeftLevelOrg/LeftLevel
* Helix project track: https://github.com/LeftLevelOrg/leftlevel-helix

## Repository structure

```text
.
├── index.html
├── vision.html
├── roadmap.html
├── docs.html
├── developers.html
├── about.html
├── projects.html
├── blog.html
├── privacy.html
├── 404.html
├── assets/
├── robots.txt
├── sitemap.xml
├── site.webmanifest
├── .htaccess
└── .github/
    └── workflows/
        └── deploy-sftp.yml
```

## Deployment

This repository deploys the static website to DreamHost using GitHub Actions and SFTP/rsync.

Deployment credentials must never be committed to the repository. They are stored only as GitHub Actions repository secrets.

Required repository secrets:

```text
SFTP_HOST
SFTP_USERNAME
SFTP_PASSWORD
SFTP_PORT
SFTP_TARGET
```

The workflow references these secret names, but the secret values are not stored in the repository.

## Security posture

The website is static and uses a hardened `.htaccess` baseline that includes:

* HTTPS hardening through HSTS
* MIME-sniffing protection
* Referrer policy
* Frame protection
* Permissions policy
* Content Security Policy

The repository also excludes local deployment files, generated ZIP files, environment files, logs, private notes, and other non-public artifacts.

## Do not commit

Do not commit any of the following:

```text
.env
.env.*
*.zip
*.log
private keys
DreamHost credentials
server account details
deployment notes
local backup files
generated probe files
```

Secrets belong only in GitHub Actions repository secrets.

## License

The website code is licensed under the MIT License.

LeftLevel names, logos, marks, and brand assets are not granted for unrelated reuse and remain part of the LeftLevel project identity.
