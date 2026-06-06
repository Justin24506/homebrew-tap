# Justin24506 Tap

A custom Homebrew tap for personal/third-party macOS applications and tools.

## Available Casks

* **Radicle** (`radicle-desktop`): Desktop client for the Radicle peer-to-peer code collaboration network.

---

## Installation

Because third-party Homebrew taps run custom package code on your system, Homebrew's security policy requires you to explicitly trust the tap before installing from it.

### Step 1: Tap and Trust the Repository
Run the following commands to add the tap and authorize it on your machine:

```bash
brew tap justin24506/tap
brew trust justin24506/tap

```

### Step 2: Install the Cask

Once the tap is trusted, you can install the application natively:

```bash
brew install --cask radicle-desktop

```

### One-Line Alternative

If you prefer to install it immediately using a fully-qualified name without tapping first, Homebrew will prompt you for trust dynamically:

```bash
brew install --cask justin24506/tap/radicle-desktop
```

### Via Brewfile

If you manage your software setup via a `Brewfile` using `brew bundle`, add these lines:

```ruby
tap "justin24506/tap"
cask "radicle-desktop"
```

*(Note: If running automated bundles, you may need to execute `brew trust justin24506/tap` prior to running `brew bundle` to prevent the installer from skipping it).*

---

## Trusting Unnotarized Apps (Gatekeeper Bypass)

Radicle Desktop is distributed directly by its developers and does not go through Apple's official App Store notarization.

My cask configuration automatically strips the macOS quarantine flag during installation. However, if macOS Gatekeeper still blocks the app from launching with an "unverified developer" warning, you can easily bypass it:

1. Open your `/Applications` folder in Finder.
2. **Right-click** (or `Control` + click) the Radicle application icon.
3. Select **Open** from the context menu.
4. Click **Open** again on the security confirmation dialog. (You will only need to do this once).

OR

You can run 
```zsh
sudo xattr -rd com.apple.quarantine /Applications/Radicle.app
```
in the terminal.

---

## Documentation

`brew help`, `man brew` or check [Homebrew's documentation](https://docs.brew.sh).
