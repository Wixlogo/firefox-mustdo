# Enhance Your Firefox Experience 🔥🦊
Essential tweaks, settings, and tools to optimize Firefox for usability, privacy, and customization.
## Install Firefox
Visit the [Firefox Website](https://www.mozilla.org/en-US/firefox/new/) and hit the big blue download button.

### Using CLI (Recommended)
#### Windows
If you're on Windows, you can use [Winget](https://apps.microsoft.com/detail/9nblggh4nns1?hl=en-us&gl=IN):
```bash
winget install Mozilla.Firefox
```

#### Mac OS
On mac you can install Firefox using [Homebrew](https://brew.sh/):
```bash 
brew install --cask firefox
```

#### Linux
Firefox might already be preinstalled on your Linux distro. It's also available as a [Flatpak package](https://flathub.org/apps/org.mozilla.firefox):
```bash 
flatpak install flathub org.mozilla.firefox
```

## Setting everything up with User.js
With a `user.js` file, you don't need to set up everything manually. Simply place the `user.js` file containing your settings into the Firefox root directory, restart Firefox, and all configurations will be applied automatically.

[Betterfox](https://github.com/yokoffing/Betterfox) is one of the most popular and well-configured `user.js` files. I recommend using my modified user.js file, as it is built upon the solid Betterfox foundation, offering additional tweaks such as improved font rendering on Windows, HTTPS-Only mode, disabled WebRTC, and more.

### Steps
1. Download the `user.js` file from [here](https://raw.githubusercontent.com/Wixlogo/firefox-mustdo/refs/heads/main/user.js) (Right click > `Save Link As…`).

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
  <img src="https://i.ibb.co/wWN3r0q/Ntt-CJBKMQf.png" alt="Black Theme" width="800">

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

- **[Windscribe VPN](https://windscribe.com/yo/40sycx18)**  
  A VPN service with 10GB/month on the free plan. _(Note: This link is my referral link.)_

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


