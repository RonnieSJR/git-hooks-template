# Git Hooks Template

This repository contains useful Git hooks for automating changelog updates and version increments.

## Contents

- `hooks/post-commit`: A post-commit hook that automatically updates CHANGELOG.md and increments the version in package.json.

## Usage

1. Clone this repository:

   ```
   git clone https://github.com/RonnieSJR/git-hooks-template.git
   ```

2. Copy the desired hook to your project's `.git/hooks/` directory:

   ```
   cp git-hooks-template/hooks/post-commit /path/to/your/project/.git/hooks/
   ```

3. Make sure the hook is executable:

   ```
   chmod +x /path/to/your/project/.git/hooks/post-commit
   ```

4. The hook will now run automatically after each commit in your project.

## Hook Details

### post-commit

This hook does the following after each commit:

1. Updates CHANGELOG.md with the new commit message and date.
2. Increments the patch version in package.json.
3. Amends the commit to include these changes.

To skip the hook for a specific commit, use the `--no-verify` flag:

```
git commit -m "Your message" --no-verify
```
