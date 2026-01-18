# Paraph

> **Paraph** (n. from French 'paraphe'): A flourish made after a signature, originally to prevent forgery.

**Paraph** is a unified wrapper designed to simplify the chaos of cross-platform binary signing. It allows you to sign and verify **macOS**, **Windows**, **Android**, and **Linux** binaries.

---

## Supported Formats

| Platform | Extension | Tool Used |
| :--- | :--- | :--- |
| **macOS** | `.dmg` | `rcodesign` |
| **Windows** | `.msix` | `osslsigncode` |
| **Android** | `.apk` | `apksigner` |
| **Linux** | `.AppImage` | `gpg` |

---

## Installation

1.  **Clone the repo:**

2.  **Make it executable:**
    ```bash
    chmod +x paraph.sh
    ```

3.  **(Optional) Install globally:**
    ```bash
    sudo mv paraph.sh /usr/local/bin/paraph
    ```

---

## Configuration

```bash
# === macOS & Windows (Shared P12) ===
export MAC_P12="/path/to/universal.p12"
export MAC_PASS="your_p12_password"
export MAC_CERT_SUBJECT="My App" # Used for verification checks

# === Android ===
export ANDROID_KEYSTORE="/path/to/android.keystore"
export ANDROID_ALIAS="my-alias"
export ANDROID_PASS="keystore_password"

# === Linux ===
export GPG_KEY_ID="my@email.com"
export GPG_PASS="passphrase"
```

---

## Usage

```bash
paraph sign application.dmg
paraph sign app-release.apk
paraph sign installer.msix
paraph sign installer.AppImage

paraph verify application.dmg
paraph verify app-release.apk
paraph verify installer.msix
paraph verify installer.AppImage
```

This project is licensed under the GNU General Public License v3.0 (GPLv3).
