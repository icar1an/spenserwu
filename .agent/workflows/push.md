---
description: Stage, commit, and push all changes to GitHub with a descriptive commit message
---

// turbo-all

## Steps

1. Check the current git status to see what files have changed:
```bash
cd /Users/sfw/Desktop/Projects/MY\ GITHUB/spenserwu && git status
```

2. Stage all changes:
```bash
cd /Users/sfw/Desktop/Projects/MY\ GITHUB/spenserwu && git add -A
```

3. Commit with a descriptive message based on what changed. Use the format `update: <brief description>`:
```bash
cd /Users/sfw/Desktop/Projects/MY\ GITHUB/spenserwu && git commit -m "update: <description of changes>"
```
Replace `<description of changes>` with a concise summary of what was modified (e.g., "restructure content, add writing entries, rename taste to curation").

4. Push to the main branch:
```bash
cd /Users/sfw/Desktop/Projects/MY\ GITHUB/spenserwu && git push origin main
```

5. Confirm the push succeeded and note that GitHub Pages typically deploys within 1-3 minutes.
