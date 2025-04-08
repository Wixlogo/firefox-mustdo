# Enhance Your Firefox Experience 🔥🦊
Essential tweaks, settings, and tools to optimize Firefox for usability, privacy, and customization.
> Note: This setup prioritizes usability and convenience while maintaining privacy. 
> For maximum privacy or anonymity, consider [Mulvad Browser](https://mullvad.net/en/browser) or the [Tor Browser](https://www.torproject.org/).  
> A well-configured Firefox `<` dedicated privacy Firefox folks in *terms of privacy*.  
> This guide (or honestly any guide) can’t fix the [security concerns of Gecko/Firefox](https://madaidans-insecurities.github.io/firefox-chromium.html).
## Install Firefox
Visit the [Firefox Website](https://www.mozilla.org/en-US/firefox/new/) and hit the big blue download button.

### Using CLI (Recommended)
#### Windows
If you're on Windows, you can choose from multiple package managers:

1. **[Winget](https://apps.microsoft.com/detail/9nblggh4nns1?hl=en-us&gl=IN)** (Pre-installed on Windows 10/11):  
   ```bash
   winget install Mozilla.Firefox
   ```

2. **[Scoop](https://scoop.sh/)**:  
   ```bash
   scoop install firefox
   ```

3. **[Chocolatey](https://chocolatey.org/)**:  
   ```bash
   choco install firefox
   ```
   
#### Mac OS
Install Firefox using [Homebrew](https://brew.sh/):
```bash 
brew install --cask firefox
```

#### Linux
Firefox might already be preinstalled on your Linux distro. If not, run these commands according to your linux distro:

1. **Debian/Ubuntu-based distributions**:  
   ```bash
   sudo apt install firefox
   ```

2. **Fedora/Red Hat-based distributions**:  
   ```bash
   sudo dnf install firefox
   ```

3. **Manjaro/Arch-based distributions**:  
   ```bash
   sudo pacman -S firefox
   ```

4. **Flatpak- Universal Package Manager** (*Not Recommended*):   
   ```bash
   flatpak install flathub org.mozilla.firefox
   ```

  > **Note:** Firefox native packages (from your distro's repository) tend to not only be faster and more stable compared to Flatpak, it's also more secure. Flatpak applications include sandboxing and isolation with the OS out of the box, offering additional security But it deliberately reduces Firefox's own default sandboxing method.  
>  
> For optimal protection even with native packages, I highly recommend taking the time to learn and configure [AppArmor](https://ubuntu.com/security/apparmor) or [SELinux](https://selinuxproject.org/page/Main_Page) based on your Linux distribution.  
> Properly configuring a Mandatory Access Control (MAC) system can provide robust protection even for native packages by limiting application privileges and preventing unauthorized access.

## Setting everything up with User.js
With a `user.js` file, you don't need to set up everything manually. Simply place the `user.js` file containing your settings into the Firefox root directory, restart Firefox, and all configurations will be applied automatically.

[Betterfox](https://github.com/yokoffing/Betterfox) is one of the most popular and well-configured `user.js` files. I recommend using my modified `user.js` file, as it is built upon the solid Betterfox foundation, offering additional [tweaks](https://github.com/yokoffing/Betterfox/wiki/Common-Overrides) and [hardening](https://github.com/yokoffing/Betterfox/wiki/Optional-Hardening) which include:  


| **Description**                                 | **Preference**                                      | **Reason**                                                                 |
|-------------------------------------------------|---------------------------------------------------|---------------------------------------------------------------------------|
| Match OS theme                                  | `layout.css.prefers-color-scheme.content-override`, `2` | Ensures websites follow the browser's theme setting (dark or light) based on OS preferences. |
| Improve font rendering using [DirectWrite](https://learn.microsoft.com/en-us/windows/win32/directwrite/direct-write-portal) | `gfx.font_rendering.cleartype_params.rendering_mode`, `5`<br>`gfx.font_rendering.cleartype_params.cleartype_level`, `100`<br>`gfx.font_rendering.cleartype_params.force_gdi_classic_for_families`, `""`<br>`gfx.font_rendering.directwrite.use_gdi_table_loading`, `false` | Makes text sharper and visually pleasing on Windows. |
| Restore search engine suggestions               | `browser.search.suggest.enabled`, `true`          | Improves usability by showing search suggestions directly in the search bar. |
| Disable Firefox Sync                            | `identity.fxaccounts.enabled`, `false`            | Prevents syncing personal data like bookmarks and history across devices for enhanced privacy. |
| Disable Firefox View tour popup                 | `browser.firefox-view.feature-tour`, `{"screen":"","complete":true}` | Avoids unnecessary distractions by skipping the feature tour.             |
| Disable login manager                           | `signon.rememberSignons`, `false`                 | Stops Firefox from saving passwords to ensure data isn't stored locally. Use any external password manager. |
| Disable address autofill                        | `extensions.formautofill.addresses.enabled`, `false` | Reduces the risk of sharing sensitive personal information automatically. |
| Disable credit card autofill                    | `extensions.formautofill.creditCards.enabled`, `false` | Prevents autofill for sensitive financial information for better security. |
| Enable HTTPS-Only Mode                          | `dom.security.https_only_mode`, `true`            | Ensures secure connections by default, protecting against HTTP risks.     |
| Warn on loading HTTP sites                      | `dom.security.https_only_mode_error_page_user_suggestions`, `true` | Provides a warning before visiting potentially insecure sites.            |
| Set DNS-over-HTTPS (DoH) provider to [Mullvad](https://mullvad.net/en/help/dns-over-https-and-dns-over-tls/) | `network.trr.uri`, `https://base.dns.mullvad.net/dns-query` | Routes DNS queries securely via [Mullvad](https://mullvad.net/en/help/dns-over-https-and-dns-over-tls/) for improved privacy. |
| Enforce DNS-over-HTTPS                          | `network.trr.mode`, `3`                           | Guarantees encrypted DNS queries for better security and anonymity.       |
| Ask where to save every file                    | `browser.download.useDownloadDir`, `false`        | Gives users control over storage location and prevents accidental downloads of malicious or unintended files. |
| Enable smooth scrolling                         | `general.smoothScroll`, `true`<br>`general.smoothScroll.pages`, `true` | Enhances browsing experience with fluid page navigation.                  |
| Disable WebRTC to prevent IP leaks              | `media.peerconnection.enabled`, `false`           | Prevents IP address leaks, as WebRTC can expose your IP even while using a VPN. |
| Disable new tab page                            | `browser.newtabpage.enabled`, `false`<br>`browser.newtab.preload`, `false` | Ensures a clean and distraction-free new tab experience.                  |
| Disable sidebar                                 | `sidebar.revamp`, `false`                         | Restores the traditional browser layout. |
| Double-click to close browser tabs              | `browser.tabs.closeTabByDblclick`, `true`          | Lets you close a tab by double-clicking on it, similar to Edge and some browsers. |
| Disable Web Search on Firefox Home              | `browser.newtabpage.activity-stream.showSearch`, `false` | Removes the web search bar from the Firefox Home tab for Blank Tab. |
| Enable Safe Browsing for downloads              | `browser.safebrowsing.downloads.remote.enabled`, `true` | Detect malicious files by comparing hashed data against a safe list, (It does not send full download information to Google). |


### Steps
1. Download the `user.js` file from [here](https://raw.githubusercontent.com/Wixlogo/firefox-mustdo/refs/heads/main/user.js) (Right click > `Save Page As…`).

2. Go to `about:profiles` in Firefox. Under **Root Directory**, click `Open Folder`.

   <img src="https://i.ibb.co/z8Xkygr/aboutprofiles.png" alt="about:profiles">

3. Paste the downloaded `user.js` file into the folder.

   <img src="https://i.ibb.co/vJvmfm6/ckv-OW4w4o-U.png" alt="user.js in File explorer">

4. Restart Firefox (Just close and open it again), and it should look like this:

   <img src="https://i.ibb.co/WPgNr1W/aftermyjs.png" alt="Firefox after my js">


## Customize Firefox
- To rearrange or remove elements, right-click on the toolbar and select `Customize Toolbar`. Drag out items as desired.

[![CUstomize Firefox]()](https://github.com/user-attachments/assets/1dc68124-dbd9-4a92-9e28-7961ec32ed10)  

- [Black by XI](https://addons.mozilla.org/en-GB/firefox/addon/black21/) is my favorite theme. It offers a pure black design.  
  <img src="https://i.ibb.co/NdnBKt79/Screenshot-2025-01-29-204542.png" alt="Black Theme" width="800">

- You can also use [Firefox Color](https://color.firefox.com/) which is an [addon](https://addons.mozilla.org/firefox/addon/firefox-color/) developed by Firefox team themselves which lets you create your own theme.
- Customize Firefox using CSS! You can make Firefox look like Chrome with [Material Fox Updated](https://github.com/edelvarden/material-fox-updated) or even the trending ARC browser with [Arc UI](https://github.com/dxdotdev/arc-ui). Check out these resources to know about Firefox-CSS:
  - [FirefoxCSS Store](https://firefoxcss-store.github.io/)
  - [r/FirefoxCSS](https://reddit.com/r/FirefoxCSS)
  - [Firefoxcsshacks](https://github.com/MrOtherGuy/firefox-csshacks)
  - [ToyfoCSS](https://mrotherguy.github.io/ToyfoCSS/) by [u/It_Was_The_Other_Guy](https://www.reddit.com/user/It_Was_The_Other_Guy/)

## Recommended Firefox Add-ons
Here are some must-have add-ons to enhance your Firefox experience:

- **[uBlock Origin](https://addons.mozilla.org/addon/ublock-origin)** [**Must Install**]  
  The best ad blocker in the world. Don't forget to enable these filter lists:
  - [r/piracy's filter recommendation](https://a.imagem.app/3HvFev.webp)  
    **OR**
  - [yokoffing's filter recommendation](https://github.com/yokoffing/filterlists?tab=readme-ov-file#recommended-filters-for-ublock-origin)

- **[FMHY-SafeGuard](https://addons.mozilla.org/en-US/firefox/addon/fmhy-safeguard/)**  
  Detects starred, safe, unsafe, or potentially unsafe sites using the FMHY Filterlist.

- **[Firefox Multi-Account Containers](https://addons.mozilla.org/firefox/addon/multi-account-containers/)**  
  Create separate cookie sessions for different websites within the same browser window.

- **[Cookie AutoDelete](https://addons.mozilla.org/firefox/addon/cookie-autodelete/)**  
  Automatically deletes unused cookies and other site data unless you whitelist specific sites.  
  Alternative: **[Temporary Containers](https://addons.mozilla.org/en-US/firefox/addon/temporary-containers/)**.

- **[Windscribe VPN](https://addons.mozilla.org/en-US/firefox/addon/windscribe/)**  
  A pretty good no-logs VPN with free 2GB/month if you enter your email and 10GB/month if you verify your email. [My referral link](https://windscribe.com/yo/40sycx18).

- **[Bitwarden](https://addons.mozilla.org/en-US/firefox/addon/bitwarden-password-manager/)**  
  A free, cross-platform password manager.

- **[Vimium-FF](https://addons.mozilla.org/en-GB/firefox/addon/vimium-ff/)**  
  Use Vim-style keyboard shortcuts in Firefox.

- **[Gesturefy](https://addons.mozilla.org/en-GB/firefox/addon/gesturefy/)**  
  Shortcuts but for mouse.

- **[Web Archives](https://addons.mozilla.org/firefox/addon/view-page-archive/)**  
  View deleted, 404 pages, or archived and cached versions of a website, can be used to access old or unavailable website/content.

---
For any query/suggestions/recommendations DM me on discord `wixlogo`


