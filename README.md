

```markdown
![Screenshot_2024-09-19_17_45_09](https://github.com/user-attachments/assets/873ef98a-48e0-445b-b5dc-eb5959ad5b34)

<div align="center">

# $${\color{orange}Burpsuite-Professional-v2026-latest}$$
</div>

<p align="center"> Burp Suite Professional is the web security tester's toolkit of choice. Use it to automate repetitive testing tasks - then dig deeper with its expert-designed manual and semi-automated security testing tools. Burp Suite Professional can help you to test for OWASP Top 10 vulnerabilities - as well as the very latest hacking techniques. Advanced manual and automated features empower users to find lurking vulnerabilities more quickly. Burp Suite is designed and used by the industry's best.</p>

<h3 align="center">

[Overview](https://portswigger.net/burp/pro)
</h3>
 
<br>
<br>

#  $${\color{magenta}Linux-Installation}$$
```sh
sudo apt update && sudo apt install -y wget && wget -qO- [https://raw.githubusercontent.com/sirajummonirshafin/bsprofational/main/install.sh](https://raw.githubusercontent.com/sirajummonirshafin/bsprofational/main/install.sh) | sudo bash

```

## Run

```sh
burpsuitepro

```

## Update

> optional

```
cd && sudo rm -rf bsprofational && wget -qO- [https://raw.githubusercontent.com/sirajummonirshafin/bsprofational/refs/heads/main/update.sh](https://raw.githubusercontent.com/sirajummonirshafin/bsprofational/refs/heads/main/update.sh) | sudo bash

```

## Java Version

> select the default openjdk runtime

```
sudo update-alternatives --config java

```

## Setup Licenses

https://github.com/sirajummonirshafin/bsprofational/assets/117867334/c25831a4-68a2-44ee-b6dd-5ff18165f340

Note: Copy the license from loader to the burpsuite > manual activation > copy burpsuite request key to loader request >  copy response key to the burpsuite.

## Shortcut Launcher - (xfce)

right click the desktop -> create a launcher name it Burpsuite Professional, add command `burpsuitepro` and select burpsuite community icon.

---

$${\color{magenta}NixOS-Installation}$$

## Add this repo's flake to your flake inputs

```
# flake.nix
{
  # ...
  inputs = {
    burpsuitepro = {
      type = "github";
      owner = "Sirajum Monir";
      repo = "bsprofational";
      inputs.nixpkgs.follows = "nixpkgs";
    };
  };
  # ...
}

```

## Installing the package provided by the flake

## You can install it with either `environment.systemPackages` or `home.packages`

> With `environment.systemPackages` (nixosModules)

```
  { inputs, ... }: {
    environment.systemPackages = [
      inputs.burpsuitepro.packages.${system}.default
    ];
  }

```

> With `home.packages` (home-manager)

```
   { inputs, ... }: {
     home.packages = [
       inputs.burpsuitepro.packages.${system}.default
     ];
   }

```

NOTE: `loader.jar` is symlinked to `burpsuite.jar` so burpsuite recognizes the license keys. You can access the `loader` command from the terminal only

---

$${\color{magenta}Windows-Installation}$$

* Make a `Burp` directory name in `C Drive` for faster access.
* Download [install.ps1](https://codeload.github.com/sirajummonirshafin/bsprofational/zip/refs/heads/main) and extract move the file inside to `C:\Burp`
* Open `Powershell` as administrator and execute below command to set Script Execution Policy.
```
Set-ExecutionPolicy -ExecutionPolicy bypass -Scope process

```


* Inside PowerShell go to `cd C:\Burp`
* Now Execute `install.ps1` file in Powershell to Complete Installation.
```
./install.ps1

```


* Change the icon of `Burp-Suite-Pro.vbs` to the given icon
* Create a shortcut to Desktop. Right Click over `Burp-Suite-Pro.vbs` Go to Shortcut tab, and below there is `Change Icon` tab
* Click there and choose the `burp-suite.ico` from `C:\Burp\`

* For Start Menu Entry, copy `Burp-Suite-Pro.vbs` file to
```
C:\ProgramData\Microsoft\Windows\Start Menu\Programs\

```



---

$${\color{magenta}MacOS-Installation}$$

## Step 1: Install Dependencies with Homebrew

Install Homebrew and required dependencies (`git`, `openjdk@17`).

```bash
/bin/bash -c "$(curl -fsSL [https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh](https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh))"
brew install git openjdk@17

```

## Step 2: Run the Installation Script

Clone the Burp Suite Professional repository, download the Burp Suite JAR file, and execute the key generator and Burp Suite.

```bash
curl -fsSL [https://raw.githubusercontent.com/sirajummonirshafin/bsprofational/main/install_macos.sh](https://raw.githubusercontent.com/sirajummonirshafin/bsprofational/main/install_macos.sh) | bash

```

## Step 3: Install the `burp` Shortcut

Make the `burp` script executable and install it globally.

```bash
chmod +x burp
sudo cp burp /usr/local/bin/burp

```

**Explanation**:

* The `installmacos.sh` script creates a `burp` script to run Burp Suite with required Java options.
* Uses `$(pwd)` to reference JAR files in the current directory.
* Makes the script executable and copies it to `/usr/local/bin` for global access.

## Notes

* **Running the Shortcut**: Run `burp` from the `bsprofational` directory containing `loader.jar` and `burpsuite_pro_v2025.5.6.jar`. For global use, replace `$(pwd)` with absolute paths.

## Contributors

## Credits

* Maintainer 👉 [Sirajum Monir](https://www.facebook.com/S.monir5403)
* Loader.jar 👉 [h3110w0r1d-y](https://github.com/h3110w0r1d-y/BurpLoaderKeygen)
* Script 👉 [cyb3rzest](https://github.com/cyb3rzest/Burp-Suite-Pro)

```

```
