# WakaTime Setup Instructions

This repository is now configured to automatically display your coding time statistics using WakaTime. Follow these steps to complete the setup:

## Prerequisites
- A GitHub account (you have this!)
- A WakaTime account (free or paid)

## Step 1: Create a WakaTime Account
1. Go to [https://wakatime.com/](https://wakatime.com/)
2. Sign up for a free account (or log in if you already have one)
3. Complete the onboarding process

## Step 2: Install WakaTime on Your Development Environment
You need to install the WakaTime plugin for your code editor(s):

### Popular Editor Plugins:
- **VS Code**: Install "WakaTime" extension from the marketplace
- **IntelliJ/PyCharm**: Install WakaTime plugin from Settings → Plugins
- **Sublime Text**: Install via Package Control
- **Vim/Neovim**: Follow instructions at wakatime.com/vim
- **Other editors**: Visit [https://wakatime.com/plugins](https://wakatime.com/plugins)

After installation, the plugin will ask for your API key (see next step).

## Step 3: Get Your WakaTime API Key
1. Log in to [https://wakatime.com/](https://wakatime.com/)
2. Go to [https://wakatime.com/settings/account](https://wakatime.com/settings/account)
3. Scroll down to find your **Secret API Key**
4. Copy this key (keep it secure!)

## Step 4: Add API Key to GitHub Secrets
1. Go to your GitHub repository: `https://github.com/31780/31780.github.io`
2. Click on **Settings** (repository settings, not your profile)
3. In the left sidebar, click **Secrets and variables** → **Actions**
4. Click **New repository secret**
5. Name: `WAKATIME_API_KEY`
6. Value: Paste your WakaTime API key
7. Click **Add secret**

## Step 5: Enable GitHub Actions
1. Go to the **Actions** tab in your repository
2. If Actions are disabled, click the button to enable them
3. The workflow should appear as "WakaTime Stats Update"

## Step 6: Test the Integration
You can manually trigger the workflow to test it:

1. Go to **Actions** tab
2. Click on "WakaTime Stats Update" workflow
3. Click **Run workflow** button
4. Select the branch (likely `main` or `master`)
5. Click **Run workflow**

The workflow will fetch your WakaTime stats and update the `index.md` file automatically.

## Step 7: Wait for Data to Accumulate
- WakaTime needs some coding activity to display stats
- Start coding in any project with the WakaTime plugin installed
- After a few hours of coding, you'll see data appear on your GitHub page
- The stats update automatically every day at midnight UTC

## What Gets Displayed
The WakaTime integration will show:
- **Languages**: Time spent in each programming language
- **Editors**: Which editors you use and for how long
- **Operating Systems**: Development environment breakdown
- **Total Time**: Weekly coding time
- **Daily Breakdown**: Time spent coding each day

## Privacy Settings
To control what's displayed:
1. Go to [https://wakatime.com/settings/profile](https://wakatime.com/settings/profile)
2. Adjust your privacy settings:
   - Make your coding activity public or private
   - Show/hide project names
   - Show/hide specific languages or editors

**Recommended for GitHub Page**: Enable public stats but hide project names to show activity without revealing private work details.

## Troubleshooting

### Stats Not Updating
- Verify your `WAKATIME_API_KEY` secret is set correctly
- Check that GitHub Actions are enabled
- Ensure you have coding activity in WakaTime (check wakatime.com dashboard)
- Look at the Actions tab for any error messages

### Plugin Not Tracking
- Verify the WakaTime plugin is installed and enabled in your editor
- Check that you entered the API key correctly in the plugin
- Restart your editor after installation
- Check [https://wakatime.com/dashboard](https://wakatime.com/dashboard) to see if activity is being tracked

### Want to Hide Certain Projects
- Go to WakaTime settings
- Add project names to your exclusion list
- Private projects won't show their names by default

## Additional Resources
- [WakaTime Documentation](https://wakatime.com/help)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [waka-readme Action](https://github.com/athul/waka-readme)

## Current Configuration
The workflow is set to:
- Update daily at midnight UTC
- Show last 7 days of activity
- Display total time and detailed breakdown
- Use progress bars for visual representation

You can customize these settings by editing `.github/workflows/wakatime.yml`.

---

Once you complete these steps, your GitHub page will automatically showcase your coding activity from all your projects (including private ones) without revealing any sensitive code or project details!
