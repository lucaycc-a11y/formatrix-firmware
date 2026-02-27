# ⌨️ FORM.MATRIX

**Split Wireless Keyboard** | FORM LABS Private Project

---

## 🏷️ Identity

```
FORM.MATRIX
LOGIC TAKES FORM
```

**Bluetooth Name:** `FORM.MATRIX`

---

## ⚙️ Specifications

| Feature | Value |
|---------|-------|
| **Type** | Split Wireless Keyboard |
| **Controller** | Pro Micro NRF52840 (nice!nano V2.0) |
| **Keys** | 60 total (30 per side) |
| **Connection** | Bluetooth 5.0 + USB |
| **Battery** | Built-in charging (nice!nano) |
| **Layers** | 4 programmable layers |

---

## 📋 Layer Layout

### Layer 0: Default (QWERTY)
```
|  `   |  1  |  2  |  3  |  4  |  5  |   |  6  |  7  |  8  |  9  |  0  | BKSP |
| TAB  |  Q  |  W  |  E  |  R  |  T  |   |  Y  |  U  |  I  |  O  |  P  |  \   |
| ESC  |  A  |  S  |  D  |  F  |  G  |   |  H  |  J  |  K  |  L  |  ;  |  '   |
| SHFT |  Z  |  X  |  C  |  V  |  B  |   |  N  |  M  |  ,  |  .  |  /  | ENT  |
| CTRL | ALT | GUI | LOW | SPC | SPC |   | SPC | SPC | RAIS|  ←  |  ↓  |  →   |
```

### Layer 1: Function Keys (hold LOWER)
```
|  F1  |  F2 |  F3 |  F4 |  F5 |  F6 |   |  F7 |  F8 |  F9 | F10 | F11 | F12  |
|      |     |     |     |     |     |   |     |     |     |     |     |      |
| CAPS |     |     |  (  |  )  |     |   |     |  [  |  ]  |  -  |  =  |      |
|      |     |     |     |     |     |   |     |     |     |     |     |      |
|      |     |     |     | DEL | DEL |   | DEL | DEL | ADJ |HOME | PGUP| END  |
```

### Layer 2: Bluetooth (hold RAISE)
```
| BT1  | BT2 | BT3 | BT4 | BT5 | CLR |   |     |     |     |     |     |      |
|      |     |     |     |     |     |   |     |     |     |     |     |      |
|      |     |     |     |     |     |   |     |     |     |     |     |      |
|      |     |     |     |     |     |   |     |     |     |     |     |      |
|      |     |     | ADJ |     |     |   |     |     |     |     |     |      |
```

### Layer 3: Reset (LOWER + RAISE)
```
|RESET |     |     |     |     |     |   |     |     |     |     |     |      |
|      |     |     |     |     |     |   |     |     |     |     |     |      |
|      |     |     |     |     |     |   |     |     |     |     |     |      |
|      |     |     |     |     |     |   |     |     |     |     |     |      |
|      |     |     |     |     |     |   |     |     |     |     |     |      |
```

---

## 🚀 How to Build

### Method 1: GitHub Actions (Recommended)

1. **Create GitHub Repo**
   ```bash
   # Go to github.com/new
   # Name: formatrix-firmware
   # Public repository
   ```

2. **Upload Files**
   ```bash
   cd formatrix-firmware
   git init
   git add .
   git commit -m "FORM.MATRIX firmware"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/formatrix-firmware.git
   git push -u origin main
   ```

3. **Enable Actions & Build**
   - Go to Actions tab
   - Enable workflows
   - Wait ~5 minutes

4. **Download Firmware**
   - Actions → Completed workflow → Artifacts
   - Download `firmware.zip`
   - Extract `.uf2` files

---

## 🔌 How to Flash

### Step 1: Enter Bootloader

**Method A: Reset Button**
- Double-tap reset button on nice!nano

**Method B: Key Combo (if reset broken)**
- Hold LOWER + RAISE
- Press top-left key (RESET)

### Step 2: Flash Firmware

1. USB drive named `NICENANO` will appear
2. Drag & drop `.uf2` files:
   - `formatrix_left...uf2` → **left half**
   - `formatrix_right...uf2` → **right half**
3. Keyboard restarts automatically

---

## 📱 Bluetooth Pairing

### Pair New Device
1. Hold **RAISE** layer
2. Press **BT1** / **BT2** / **BT3** / **BT4** / **BT5**
3. Pair from your device
4. Device name: **FORM.MATRIX**

### Clear Bluetooth
1. Hold **RAISE** layer
2. Press **BT_CLR**

### Switch Devices
1. Hold **RAISE** layer
2. Press **BT1** - **BT5**

---

## 🔧 Customization

### Edit Keymap
Edit `config/formatrix.keymap` to customize keys.

### Common Codes
```
&kp Q           # Press Q
&mo 1           # Momentary layer 1
&bt BT_SEL 0    # Select BT device 0
&bootloader     # Enter bootloader
&trans          # Transparent (pass through)
```

### Add More Features
Edit `config/boards/shields/formatrix/formatrix.conf`:
```
# Enable RGB underglow
CONFIG_ZMK_RGB_UNDERGLOW=y

# Change idle timeout
CONFIG_ZMK_IDLE_TIMEOUT=600000  # 10 minutes
```

---

## 📂 File Structure

```
formatrix-firmware/
├── .github/
│   └── workflows/
│       └── build.yml          # GitHub Actions
├── config/
│   ├── boards/shields/formatrix/
│   │   ├── formatrix.dtsi     # Matrix definition
│   │   ├── formatrix.keymap   # Key layout ⭐
│   │   ├── formatrix_left.overlay
│   │   ├── formatrix_right.overlay
│   │   ├── formatrix_left.conf
│   │   ├── formatrix_right.conf
│   │   ├── formatrix.conf
│   │   ├── Kconfig.shield
│   │   └── Kconfig.defconfig
│   ├── west.yml
│   └── formatrix.json         # Keyboard metadata
├── build.yaml                 # Build matrix
└── README.md
```

---

## 🎨 Branding

### Logo Concept
```
┌──────┐  ┌──────┐
│ FORM │  │MATRIX│
│  ▪   │  │   ▪  │
└──────┘  └──────┘
  LEFT      RIGHT
```

### Colors
- Primary: Matte Black (#000000)
- Accent: Electric Blue (#0066FF)
- LED: Blue glow

---

## 📝 Notes

### Reset Without Button
If reset button broken:
1. Hold LOWER + RAISE
2. Press top-left key
3. Enter bootloader
4. Flash new firmware

### Battery
- nice!nano V2.0 has built-in charging
- Connect USB to charge
- Battery level shown in OS

---

## 🙏 Credits

- **Project:** FORM LABS
- **Based on:** Caldera Keyboard by Christian Selig
- **Firmware:** ZMK (Zephyr Mechanical Keyboard)
- **Designed by:** Luca Yau

---

**LOGIC TAKES FORM** 🔷

*FORM.MATRIX - 2026*
