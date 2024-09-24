# Git Hooks Template

This repository contains useful Git hooks for automating changelog updates and version increments.

## Contents

- `hooks/post-commit`: A post-commit hook that automatically updates CHANGELOG.md and increments the version in package.json.

## Usage

1. Clone this repository:

   ```bash
   git clone https://github.com/RonnieSJR/git-hooks-template.git
   ```

2. Copy the desired hook to your project's `.git/hooks/` directory:

   ```bash
   cp git-hooks-template/hooks/post-commit /path/to/your/project/.git/hooks/
   ```

3. Make sure the hook is executable:

   ```bash
   chmod +x /path/to/your/project/.git/hooks/post-commit
   ```

4. Create a CHANGELOG.md file:

   ```bash
   touch /path/to/your/project/CHANGELOG.md
   ```

5. The hook will now run automatically after each commit in your project.

## Hook Details

### post-commit

This hook does the following after each commit:

1. Updates CHANGELOG.md with the new commit message and date.
2. Increments the patch version in package.json.
3. Amends the commit to include these changes.

To skip the hook for a specific commit, use the `--no-verify` flag:

```bash
git commit -m "Your message" --no-verify
```

### Uninstalling/Removing the Hook

To remove the post-commit hook from your project:

1. Delete the hook file:

   ```bash
   rm /path/to/your/project/.git/hooks/post-commit
   ```

2. If you've made commits using this hook, be aware that your CHANGELOG.md and package.json files have been automatically modified. You may want to review these files and adjust them as needed.

### Responsibility Notice

Please use this hook responsibly and understand its implications:

- It modifies your commits automatically, which may affect your project's history.
- It assumes a specific project structure (presence of CHANGELOG.md and package.json).
- Always review the changes made by the hook to ensure they align with your project's needs.

If you're working in a team, make sure all team members are aware of and agree to use this hook.
