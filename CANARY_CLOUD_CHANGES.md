# Canary Cloud Rebranding Summary

This document summarizes all changes made to rebrand Nextcloud Talk Desktop to Canary Cloud Talk Desktop.

## Changes Made

### 1. Branding Configuration (`build/config.json`)
- **Application Name**: Changed from "Nextcloud Talk" to "Canary Cloud Talk"
- **Domain**: Set to "https://talk.thalizar.info" with enforced domain connection
- **Brand Color**: Changed from #0082C9 (Nextcloud Blue) to #FFD700 (Canary Yellow)
- **Brand Font Color**: Changed from #FFFFFF to #000000 for better contrast on yellow
- **Help URL**: Updated to https://talk.thalizar.info/
- **Privacy URL**: Updated to https://talk.thalizar.info/privacy/
- **macOS DMG**: Disabled (set to false)

### 2. Package Metadata (`package.json`)
- **Product Name**: "Canary Cloud Talk"
- **Desktop Name**: "com.canarycloud.talk.desktop"
- **Repository URLs**: Updated to QuizzityMC/talk-desktop-canary

### 3. Visual Branding

#### Logos Created
All SVG logos were replaced with custom Canary Cloud themed designs featuring:
- Yellow gradient speech bubble icon (#FFD700 to #FFA500)
- "CANARY CLOUD" and "TALK" branding text

Files updated:
- `img/talk-logo.svg` - Main logo
- `img/talk-logo-spaced.svg` - Logo with spacing
- `img/talk-icon-rounded.svg` - Rounded icon
- `img/talk-icon-rounded-spaced.svg` - Rounded icon with spacing
- `img/talk-icon-square.svg` - Square icon
- `img/talk-icon-plain-dark.svg` - Plain icon for dark themes
- `img/talk-icon-plain-light.svg` - Plain icon for light themes
- `img/talk-icon-plain-spaced-dark.svg` - Spaced plain icon for dark themes
- `img/talk-icon-plain-spaced-light.svg` - Spaced plain icon for light themes
- `img/talk-icon-mac.svg` - macOS specific icon
- `img/talk-icon-mac-shadow.svg` - macOS icon with shadow
- `img/server-logo-plain.svg` - Server logo

#### Icons Generated
Using the new SVG sources, generated all required icon formats:
- **Linux**: PNG icons (512x512) and tray icons
- **macOS**: ICNS format with multiple sizes (16-1024px)
- **Windows**: ICO format with multiple sizes (16-256px)
- **Tray icons**: Platform-specific system tray icons in light and dark variants

### 4. UI Changes
- **Welcome Screen** (`src/welcome/welcome.html`):
  - Background color: Changed from #00679E (blue) to #FFD700 (yellow)
  - Text color: Changed from white to black for visibility

### 5. Documentation (`README.md`)
- Updated title to "Canary Cloud Talk Desktop"
- Removed Nextcloud-specific badges and links
- Updated description to reference Canary Cloud instance
- Simplified installation instructions to reference local releases
- Updated prerequisites to mention Canary Cloud

### 6. Build Process
- Used Nextcloud Talk v22.0.0 as the base Talk application
- Built for Linux x64 and Windows x64 platforms
- Generated portable ZIP packages for both platforms

## Build Artifacts

### Release Files (in `releases/` directory)

1. **Canary.Cloud.Talk-linux-x64.zip** (179 MB)
   - Linux x64 portable application
   - Extract and run `Canary Cloud Talk` executable

2. **Canary.Cloud.Talk-windows-x64.zip** (189 MB)
   - Windows x64 portable application
   - Extract and run `Canary Cloud Talk.exe`

Both packages include:
- Pre-configured connection to https://talk.thalizar.info/
- Enforced domain (cannot connect to other servers)
- Canary Yellow branding throughout
- Custom Canary Cloud logo and icons

## Application Features

- **Enforced Domain**: Application only connects to talk.thalizar.info
- **Custom Branding**: Yellow theme with Canary Cloud logo
- **Full Talk Features**: All Nextcloud Talk v22.0.0 features included
- **Desktop Integration**: System tray, notifications, etc.

## Creating a GitHub Release

To publish these builds:

1. Go to GitHub repository releases page
2. Click "Create a new release"
3. Tag version: v2.0.2-canary
4. Release title: "Canary Cloud Talk Desktop v2.0.2"
5. Upload the two ZIP files from the `releases/` directory:
   - Canary.Cloud.Talk-linux-x64.zip
   - Canary.Cloud.Talk-windows-x64.zip
6. Add release notes describing the Canary Cloud branding

## Technical Details

- **Base Version**: Nextcloud Talk Desktop 2.0.2
- **Talk Version**: v22.0.0
- **Build Platform**: Linux
- **Node Version**: v20.19.5
- **Electron**: v38.2.1

## Known Limitations

- **macOS builds**: Not included (would require macOS build environment)
- **Linux installers**: Flatpak not built (requires flatpak-builder tools)
- **Windows installers**: EXE/MSI not built (requires Wine/Mono on Linux)
- **Logo source**: Created as placeholder SVG (original logo URL was inaccessible)

## Next Steps

If you need:
- **The original Canary logo**: Replace the SVG files in `img/` directory and re-run `npm run generate-icons`
- **macOS builds**: Build on a macOS machine using `npm run build:mac`
- **Native installers**: Build on respective platforms or set up Wine/Mono for Windows
- **Flatpak**: Install flatpak-builder and run `npm run package:linux`

## Files Modified

- `build/config.json` - Build configuration
- `package.json` - Package metadata
- `README.md` - Documentation
- `src/welcome/welcome.html` - Welcome screen styling
- `img/*.svg` - All logo and icon files
- `.gitignore` - Added releases, out, and spreed directories
