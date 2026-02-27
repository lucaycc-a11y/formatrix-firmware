# 🚀 Quick Start - FORM.MATRIX

## Step 1: Create GitHub Repo

1. Go to https://github.com/new
2. Repository name: `formatrix-firmware`
3. Description: `FORM.MATRIX Split Wireless Keyboard Firmware`
4. Public ✅
5. **Don't** initialize with README (we have one)
6. Click "Create repository"

## Step 2: Upload to GitHub

Open Terminal and run:

```bash
# Go to folder
cd ~/Downloads
# Extract the zip first if not done

# Initialize git
cd formatrix-firmware
git init
git add .
git commit -m "FORM.MATRIX firmware - Initial commit"

# Add your remote (REPLACE YOUR-USERNAME!)
git remote add origin https://github.com/YOUR-USERNAME/formatrix-firmware.git
git branch -M main
git push -u origin main
```

If asked, login with:
- Username: your GitHub username
- Password: use Personal Access Token (not your password)
  - Generate at: github.com/settings/tokens

## Step 3: Enable Actions

1. Go to your repo
2. Click "Actions" tab
3. Click "I understand my workflows, go ahead and enable them"

## Step 4: Download Firmware

1. Wait ~5 minutes
2. Click "Actions" → Click completed workflow
3. Scroll to "Artifacts" at bottom
4. Download `firmware.zip`
5. Extract files

## Step 5: Flash to Keyboard

### Left Half:
1. Connect left half via USB
2. Double-tap reset button (or hold LOWER+RAISE + top-left)
3. Drag `formatrix_left-nice_nano_v2.uf2` to NICENANO drive

### Right Half:
1. Connect right half via USB
2. Double-tap reset button
3. Drag `formatrix_right-nice_nano_v2.uf2` to NICENANO drive

## Done! 🎉

Your keyboard will appear as **FORM.MATRIX** in Bluetooth devices.

---

## Troubleshooting

### Git push failed?
```
# If asked for password, use Personal Access Token
# Generate at: github.com/settings/tokens/new
# Select: repo (all)
# Copy token and paste as password
```

### Build failed?
- Check Actions tab for error
- Make sure all files uploaded
- Try re-running workflow

### Can't find .uf2 files?
- Check Artifacts section in Actions
- Firmware might still be building
- Refresh page

---

Need help? Ask Nova! 🤖
