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

# $${\color{magenta}Linux-Installation}$$

```sh
sudo apt update && sudo apt install -y wget && wget -qO- https://raw.githubusercontent.com/sirajummonirshafin/bsprofational/main/install.sh | sudo bash
RunBashburpsuitepro
UpdateoptionalBashcd && sudo rm -rf bsprofational && wget -qO- https://raw.githubusercontent.com/sirajummonirshafin/bsprofational/refs/heads/main/update.sh | sudo bash
Java Versionselect the default openjdk runtimeBashsudo update-alternatives --config java
Setup Licenseshttps://github.com/sirajummonirshafin/bsprofational/assets/117867334/c25831a4-68a2-44ee-b6dd-5ff18165f340Note: Copy the license from loader to the burpsuite > manual activation > copy burpsuite request key to loader request > copy response key to the burpsuite.Shortcut Launcher - (xfce)right click the desktop -> create a launcher name it Burpsuite Professional, add command burpsuitepro and select burpsuite community icon.$${\color{magenta}NixOS-Installation}$$Add this repo's flake to your flake inputsNix# flake.nix
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
Installing the package provided by the flakeYou can install it with either environment.systemPackages or home.packagesWith environment.systemPackages (nixosModules)Nix{ inputs, ... }: {
  environment.systemPackages = [
    inputs.burpsuitepro.packages.${system}.default
  ];
}
With home.packages (home-manager)Nix{ inputs, ... }: {
  home.packages = [
    inputs.burpsuitepro.packages.${system}.default
  ];
}
NOTE: loader.jar is symlinked to burpsuite.jar so burpsuite recognizes the license keys. You can access the loader command from the terminal only$${\color{magenta}Windows-Installation}$$Make a Burp directory name in C Drive for faster access.Download install.ps1 and extract move the file inside to C:\BurpOpen Powershell as administrator and execute below command to set Script Execution Policy.PowerShellSet-ExecutionPolicy -ExecutionPolicy bypass -Scope process
Inside PowerShell go to cd C:\BurpPowerShellcd C:\Burp
Now Execute install.ps1 file in Powershell to Complete Installation.PowerShell./install.ps1
Change the icon of Burp-Suite-Pro.vbs to the given iconCreate a shortcut to Desktop. Right Click over Burp-Suite-Pro.vbs Go to Shortcut tab, and below there is Change Icon tabClick there and choose the burp-suite.ico from C:\Burp\For Start Menu Entry, copy Burp-Suite-Pro.vbs file to:PlaintextC:\ProgramData\Microsoft\Windows\Start Menu\Programs\
$${\color{magenta}MacOS-Installation}$$Step 1: Install Dependencies with HomebrewInstall Homebrew and required dependencies (git, openjdk@17).Bash/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install git openjdk@17
Step 2: Run the Installation ScriptClone the Burp Suite Professional repository, download the Burp Suite JAR file, and execute the key generator and Burp Suite.Bashcurl -fsSL https://raw.githubusercontent.com/sirajummonirshafin/bsprofational/main/install_macos.sh | bash
Step 3: Install the burp ShortcutMake the burp script executable and install it globally.Bashchmod +x burp
sudo cp burp /usr/local/bin/burp
Explanation:The installmacos.sh script creates a burp script to run Burp Suite with required Java options.Uses $(pwd) to reference JAR files in the current directory.Makes the script executable and copies it to /usr/local/bin for global access.NotesRunning the Shortcut: Run burp from the bsprofational directory containing loader.jar and burpsuite_pro_v2025.5.6.jar. For global use, replace $(pwd) with absolute paths.ContributorsCreditsMaintainer 👉 Sirajum MonirLoader.jar 👉 h3110w0r1d-yScript 👉 cyb3rzest
