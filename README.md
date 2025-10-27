<!--
  - SPDX-FileCopyrightText: 2022 Nextcloud GmbH and Nextcloud contributors
  - SPDX-License-Identifier: CC0-1.0
-->

# Canary Cloud Talk Desktop

> Desktop client for Canary Cloud Talk (Nextcloud Talk instance at https://talk.thalizar.info/)

## 📥 Install

Download the latest release for your platform:

| Platform (arch)          | Distribution type                                     | Download link                                                  |
|--------------------------|-------------------------------------------------------|----------------------------------------------------------------|
| **🐧 Linux** (x64)       | Flatpak single file (recommended)                     | Available from releases                                        |
| **🐧 Linux** (x64)       | ZIP archive                                           | Available from releases                                        |
| **🪟 Windows** (x64)     | Non-admin single-user one-click installer            | Available from releases                                        |
| **🪟 Windows** (x64)     | MSI (for administrated environments)                  | Available from releases                                        |

## 🏗️ Prerequisites

- [Nextcloud Server](https://github.com/nextcloud/server) version 27 or higher.
- [Nextcloud Talk](https://github.com/nextcloud/spreed) version 17 or higher.

## 👥 Multi-account

Full multi-account currently [is not currently supported](https://github.com/nextcloud/talk-desktop/issues/7).

However, using portable `zip` distribution, you can have several Nextcloud Talk instances run simultaneously. Just rename the executable from default  `Nextcloud Talk` to a custom name. For example: 

```
/path/to/apps/
├── home-apps/
│   └── Nextcloud Talk/
│       ├── ...
│       ├── Nextcloud Talk (Home).exe
│       └── ...
└── work-apps/
    └── Nextcloud Talk/
        ├── ...
        ├── Nextcloud Talk (Work).exe
        └── ...
```

## 🛠️ Development Setup

1. Install dependencies
	 ```bash
	 npm ci 
	 ```
2. Nextcloud Talk Desktop requires [Nextcloud Talk source code](https://github.com/nextcloud/spreed).
   - **No `nextcloud/spreed` is cloned?**\
     Clone it and install dependencies:
	   ```sh
	   # Clone Talk to the repository root
	   git clone https://github.com/nextcloud/spreed
     
	   # Install dependencies
	   npm ci --prefix=spreed
	   ```
   - **You want to reuse existing `nextcloud/spreed`, for instance, in a server setup?**\
     Set `TALK_PATH` ENV variable or edit `.env` file:
     ```sh
     cp .env.example .env
     # Edit .env and set TALK_PATH
     TALK_PATH=/path/to/nextcloud/server/apps-extra/spreed/
     ```
3. Check `.env.example` for any additional configuration if needed.

## 🧑‍💻 Development

### Start development server in Electron

```bash
npm run dev
```

### Build binaries for production

```bash
# 🖥️ Current platform and architecture
npm run build

# 🐧 Linux (x64)
npm run build:linux

# 🍏 macOS (universal)
npm run build:mac
# 🍏 macOS (separate x64 and arm64)
npm run build:mac:x64
npm run build:mac:arm64

# 🪟 Windows (win32-x64)
npm run build:windows
```

Notes:
- **General recommendation is to always build binaries on the same platform**
- Building Windows binaries on Linux/Mac requires Wine
- Building Mac binaries on Windows is not supported
- Building Linux binaries on Windows is not supported for some Linux distributions

### Maintenance

#### Generating icons

After changing source icons, to generate icons in different sizes and formats, run:

```bash
npm run generate-icons
```

#### Updating global (server) styles

Talk frontend depends on the global Nextcloud server styles. To manually get them run:

```bah
# node ./scripts/fetch-server-styles.mjs <VERSION>, for example
node ./scripts/fetch-server-styles.mjs stable29
```

## 📦 Packaging distributions

```bash
# 🐧 Linux (x64)
npm run package:linux

# 🍏 macOS (universal)
npm run package:mac
# 🍏 macOS (separate x64 and arm64)
npm run package:mac:arm64
npm run package:mac:x64

# 🪟 Windows (win32-x64)
npm run package:windows
```

## 👥 Contribution Guidelines

See: https://github.com/nextcloud/spreed#contribution-guidelines
