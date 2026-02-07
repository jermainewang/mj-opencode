# Install Instructions for AI Agent

**Goal:** Install the `mj-opencode` configuration for the user.

**Step 1: Ask User for Installation Location**

Ask the user: "Where would you like to install the configuration?
1. Global (applies to all projects) - Installs to `~/.config/opencode`
2. Project (applies to this project only) - Installs to `./.opencode`"

**Step 2: Install based on user choice**

**If Global (`~/.config/opencode`):**
1.  Check if `~/.config/opencode` exists.
2.  If it exists:
    *   Ask user if they want to overwrite existing configuration or merge.
    *   If overwrite: backup existing config (e.g., to `~/.config/opencode.bak`), then clone.
    *   If merge: clone to a temp dir and copy files over.
3.  If it doesn't exist:
    *   `git clone https://github.com/jermainewang/mj-opencode.git ~/.config/opencode`

**If Project (`./.opencode`):**
1.  Check if `./.opencode` exists.
2.  If it exists:
    *   Ask user if they want to overwrite existing configuration or merge.
    *   If overwrite: backup existing config (e.g., to `./.opencode.bak`), then clone.
    *   If merge: clone to a temp dir and copy files over.
3.  If it doesn't exist:
    *   `git clone https://github.com/jermainewang/mj-opencode.git .opencode`

**Step 3: Verify Installation**
1.  List the files in the installation directory (`ls -R <install_dir>/skills`) to confirm success.
2.  Tell the user installation is complete.
