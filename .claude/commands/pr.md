Full PR workflow:

1. **Verify** — Open index.html in browser, check for visual issues
2. **Check for uncommitted changes** — `git status`
3. **Stage and commit** — Stage relevant files, write a conventional commit message
4. **Push** — `git push -u origin HEAD`
5. **Create PR** — Use `gh pr create` with:
   - Clear title (under 70 chars)
   - Body with ## Summary (bullet points of changes) and ## Test Plan
6. **Report** — Share the PR URL
