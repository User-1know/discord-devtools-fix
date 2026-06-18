# discord-devtools-fix
A simple guide to force-enable Ctrl+Shift+I (Inspect Element) in Discord.
# How to Force Enable Discord Developer Tools (Inspect Element)

If `Ctrl + Shift + I` or `F12` does not open the developer tools in your Discord desktop client, you can force it to enable by modifying your local configuration file.

---

## ⚠️ CRITICAL SAFETY WARNING
**DO NOT copy and paste mysterious scripts or tokens given to you by strangers into your console.** Enabling developer tools allows you to look under the hood of Discord, but malicious scripts can completely steal your Discord account token, bypass your password, and lock you out. Only run scripts if you completely understand the code or trust the source 100%.

---

## The Solution

You need to insert a specific developer flag into your local Discord `settings.json` file. 

### Step 1: Get the required code
Instead of writing it from scratch, you can copy the full file structure directly from this repository:
👉 **[Click here to view the complete settings.json file](./settings.json)**

### Step 2: Locate your local file
Close Discord completely (make sure it's not hidden in your system tray/background). Then navigate to the configuration folder based on your Operating System:

* **Windows:** Press `Windows Key + R`, type `%appdata%\discord` and press Enter. Look for `settings.json`.
* **Mac:** Open Finder, navigate to `~/Library/Application Support/discord`, and look for `settings.json`.
* **Linux:** Depending on your package manager, check one of these paths:
  * **Standard (.deb / Tarball):** `~/.config/discord/settings.json`
  * **Flatpak:** `~/.var/app/com.discordapp.Discord/config/discord/settings.json`
  * **Snap:** `~/snap/discord/current/.config/discord/settings.json`

### Step 3: Apply the modification
Open your local `settings.json` file using any basic text editor (like Notepad, TextEdit, or Nano). Inside the main curly brackets `{ ... }`, add this line at the bottom:

```json
"DANGEROUS_ENABLE_DEVTOOLS_ONLY_ENABLE_IF_YOU_KNOW_WHAT_YOURE_DOING": true
