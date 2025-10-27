# How to Create a GitHub Release

The Linux and Windows builds have been successfully created. Follow these steps to publish them as a GitHub Release:

## Step 1: Locate the Release Files

The release files are located in the `releases/` directory:

```
releases/
├── Canary.Cloud.Talk-linux-x64.zip (179 MB)
├── Canary.Cloud.Talk-windows-x64.zip (189 MB)
└── README.md
```

**Note:** These files are NOT in the git repository due to their size. You'll need to access them from the build machine or download them separately.

## Step 2: Create a GitHub Release

1. **Navigate to the repository:**
   - Go to https://github.com/QuizzityMC/talk-desktop-canary

2. **Access Releases:**
   - Click on "Releases" in the right sidebar
   - Click "Create a new release" or "Draft a new release"

3. **Configure the Release:**
   - **Tag version:** `v2.0.2-canary`
   - **Release title:** `Canary Cloud Talk Desktop v2.0.2`
   - **Description:** Use the following template:

```markdown
# Canary Cloud Talk Desktop v2.0.2

Desktop application for Canary Cloud Talk, branded for the Canary Cloud instance at https://talk.thalizar.info/

## Features

✨ **Custom Branding**
- Canary Yellow theme (#FFD700)
- Custom Canary Cloud logo
- Pre-configured for talk.thalizar.info

🔒 **Security**
- Enforced domain connection (only connects to talk.thalizar.info)
- Built on Nextcloud Talk v22.0.0

💬 **Full Talk Features**
- Video and voice calls
- Chat messaging
- Screen sharing
- File sharing
- Desktop notifications

## Downloads

| Platform | File | Size |
|----------|------|------|
| Linux x64 | Canary.Cloud.Talk-linux-x64.zip | 179 MB |
| Windows x64 | Canary.Cloud.Talk-windows-x64.zip | 189 MB |

## Installation

### Linux
1. Download `Canary.Cloud.Talk-linux-x64.zip`
2. Extract the archive
3. Run the `Canary Cloud Talk` executable

### Windows
1. Download `Canary.Cloud.Talk-windows-x64.zip`
2. Extract the archive
3. Run `Canary Cloud Talk.exe`

## System Requirements

- **Linux:** x64 processor, modern Linux distribution
- **Windows:** Windows 10 or later, x64 processor

## Technical Details

- **Base Version:** Nextcloud Talk Desktop 2.0.2
- **Talk Version:** v22.0.0
- **Electron:** v38.2.1
- **Platform:** Linux/Windows x64

## What's Changed

- Complete rebranding to Canary Cloud
- Updated logos and icons to yellow theme
- Set domain to https://talk.thalizar.info/
- Enforced domain connection for security

For detailed changes, see [CANARY_CLOUD_CHANGES.md](./CANARY_CLOUD_CHANGES.md)
```

4. **Upload the Release Files:**
   - Drag and drop or click "Attach binaries" 
   - Upload both ZIP files:
     - `Canary.Cloud.Talk-linux-x64.zip`
     - `Canary.Cloud.Talk-windows-x64.zip`

5. **Publish:**
   - Review everything
   - Click "Publish release"

## Step 3: Verify the Release

After publishing, verify:
- Both ZIP files are downloadable
- The description displays correctly
- The tag is created properly

## Alternative: Command Line Release (Using GitHub CLI)

If you have `gh` CLI installed:

```bash
cd releases/

# Create the release
gh release create v2.0.2-canary \
  --title "Canary Cloud Talk Desktop v2.0.2" \
  --notes-file ../RELEASE_NOTES.md \
  Canary.Cloud.Talk-linux-x64.zip \
  Canary.Cloud.Talk-windows-x64.zip
```

## Accessing the Build Files

The build files are located at:
- Absolute path: `/home/runner/work/talk-desktop-canary/talk-desktop-canary/releases/`
- Relative to repository root: `./releases/`

You can also find the unzipped builds in:
- Linux: `./out/Canary Cloud Talk-linux-x64/`
- Windows: `./out/Canary Cloud Talk-win32-x64/`

## Support

For issues or questions about the release, please open an issue at:
https://github.com/QuizzityMC/talk-desktop-canary/issues
