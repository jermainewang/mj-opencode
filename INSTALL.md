# Install Instructions for AI Agent

**Goal:** Install `mj-opencode` configuration for the user.

**Step 1: Ask User for Installation Scope**
Ask: "Where would you like to install the configuration?
1. Global (applies to all projects) - Installs to `~/.config/opencode`
2. Project (applies to this project only) - Installs to `./.opencode`"

**Step 2: Install**

**Option 1: Global (`~/.config/opencode`)**

1.  **Clone:**
    Clone the repository to a subdirectory in `~/.config/opencode` to keep it organized and separate from other configs.
    ```bash
    mkdir -p ~/.config/opencode
    git clone https://github.com/jermainewang/mj-opencode.git ~/.config/opencode/mj-opencode
    ```

2.  **Symlink Skills:**
    Link the skills directory to `~/.config/opencode/skills/mj-opencode`. This makes the skills available under the `mj-opencode` namespace.
    ```bash
    mkdir -p ~/.config/opencode/skills
    ln -sfn ~/.config/opencode/mj-opencode/skills ~/.config/opencode/skills/mj-opencode
    ```

3.  **Symlink Commands:**
    Link the `interview` command to make it available as `/interview`.
    ```bash
    mkdir -p ~/.config/opencode/commands
    ln -sf ~/.config/opencode/mj-opencode/commands/interview.md ~/.config/opencode/commands/interview.md
    ```

**Option 2: Project (`./.opencode`)**

1.  **Clone:**
    Clone the repository to `.opencode/mj-opencode`.
    ```bash
    mkdir -p .opencode
    git clone https://github.com/jermainewang/mj-opencode.git .opencode/mj-opencode
    ```

2.  **Symlink Skills:**
    Link the skills directory to `.opencode/skills/mj-opencode`.
    ```bash
    mkdir -p .opencode/skills
    # Navigate to the skills directory to create a relative symlink if preferred, or use absolute path.
    # Here we use relative path for portability within the project.
    cd .opencode/skills
    ln -sfn ../mj-opencode/skills mj-opencode
    cd - > /dev/null
    ```

3.  **Symlink Commands:**
    Link the `interview` command to make it available as `/interview`.
    ```bash
    mkdir -p .opencode/commands
    cd .opencode/commands
    ln -sf ../mj-opencode/commands/interview.md interview.md
    cd - > /dev/null
    ```

**Step 3: Verify Installation**

1.  List the skills to confirm the symlink works:
    *   Global: `ls -l ~/.config/opencode/skills/mj-opencode`
    *   Project: `ls -l .opencode/skills/mj-opencode`
2.  Tell the user installation is complete and they can now use the skills (e.g., `mj-opencode/oc-help`).
