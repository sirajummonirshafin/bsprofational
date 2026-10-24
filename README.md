
```markdown
# Burpsuite-Professional-v2026-latest

![Screenshot](https://github.com/user-attachments/assets/873ef98a-48e0-445b-b5dc-eb5959ad5b34)

Burp Suite Professional is the web security tester's toolkit of choice. Use it to automate repetitive testing tasks - then dig deeper with its expert-designed manual and semi-automated security testing tools. Burp Suite Professional can help you to test for OWASP Top 10 vulnerabilities - as well as the very latest hacking techniques. Advanced manual and automated features empower users to find lurking vulnerabilities more quickly. Burp Suite is designed and used by the industry's best.

[Overview](https://portswigger.net/burp/pro)

---

## Linux Installation

```bash
sudo apt update && sudo apt install -y wget && wget -qO- https://raw.githubusercontent.com/sirajummonirshafin/bsprofational/main/install.sh | sudo bash

```

### Run

```bash
burpsuitepro

```

### Update (Optional)

```bash
cd && sudo rm -rf bsprofational && wget -qO- https://raw.githubusercontent.com/sirajummonirshafin/bsprofational/refs/heads/main/update.sh | sudo bash

```

### Java Version

Select the default openjdk runtime:

```bash
sudo update-alternatives --config java

```

---

## Setup Licenses

```text
Copy the license from loader to the burpsuite > manual activation > copy burpsuite request key to loader request > copy response key to the burpsuite.

```

---

## Shortcut Launcher (xfce)

Right click the desktop -> create a launcher name it Burpsuite Professional, add command `burpsuitepro` and select burpsuite community icon.

---

## NixOS Installation

### Add this repo's flake to your flake inputs

```nix
# flake.nix
{
  inputs = {
    burpsuitepro = {
      type = "github";
      owner = "Sirajum Monir";
      repo = "bsprofational";
      inputs.nixpkgs.follows = "nixpkgs";
    };
  };
}

```

### Installing the package provided by the flake

With `environment.systemPackages` (nixosModules):

```nix
{ inputs, ... }: {
  environment.systemPackages = [
    inputs.burpsuitepro.packages.${system}.default
  ];
}

```

With `home.packages` (home-manager):

```nix
{ inputs, ... }: {
  home.packages = [
    inputs.burpsuitepro.packages.${system}.default
  ];
}

```

```text
NOTE: loader.jar is symlinked to burpsuite.jar so burpsuite recognizes the license keys. You can access the loader command from the terminal only.

```

---

## Windows Installation

1. Make a `Burp` directory in `C Drive` for faster access:

```text
C:\Burp

```

2. Download `install.ps1` and extract/move the file inside to `C:\Burp`:

```text
https://codeload.github.com/sirajummonirshafin/bsprofational/zip/refs/heads/main

```

3. Open `PowerShell` as administrator and execute below command to set Script Execution Policy:

```powershell
Set-ExecutionPolicy -ExecutionPolicy bypass -Scope process

```

4. Inside PowerShell, navigate to the directory:

```powershell
cd C:\Burp

```

5. Execute `install.ps1` file to complete installation:

```powershell
./install.ps1

```

6. Change the icon of `Burp-Suite-Pro.vbs` to `burp-suite.ico` from `C:\Burp\`.
7. Create a shortcut to Desktop. Right Click over `Burp-Suite-Pro.vbs` -> Shortcut tab -> Change Icon -> Select `C:\Burp\burp-suite.ico`.

8. For Start Menu Entry, copy `Burp-Suite-Pro.vbs` file to:

```text
C:\ProgramData\Microsoft\Windows\Start Menu\Programs\

```

---

## MacOS Installation

### Step 1: Install Dependencies with Homebrew

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install git openjdk@17

```

### Step 2: Run the Installation Script

```bash
curl -fsSL https://raw.githubusercontent.com/sirajummonirshafin/bsprofational/main/install_macos.sh | bash

```

### Step 3: Install the `burp` Shortcut

```bash
chmod +x burp
sudo cp burp /usr/local/bin/burp

```

---

## Credits & Maintainer

```text
Maintainer: Sirajum Monir (https://www.facebook.com/S.monir5403)
Loader.jar: h3110w0r1d-y (https://github.com/h3110w0r1d-y/BurpLoaderKeygen)
Script: cyb3rzest (https://github.com/cyb3rzest/Burp-Suite-Pro)

```

```

```
