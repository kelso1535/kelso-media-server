# Remaining Jellyfin References

This report lists remaining occurrences of the string "Jellyfin" in the repository that were intentionally left unchanged because they are considered internal identifiers, repository/package references, automation keys, or otherwise risky to change.

Do NOT change these automatically unless you explicitly want to and understand the downstream implications (CI, package IDs, URLs, namespaces).

Representative files and why they were left unchanged:

- `.devcontainer/install-ffmpeg.sh` — references the upstream apt repository and package names (`repo.jellyfin.org`, `jellyfin-ffmpeg`). These are external URLs/package names and must remain.
- `.github/CODEOWNERS` — paths include project filenames (`Jellyfin.Data/...`) used by code ownership rules.
- `.github/workflows/*` — CI workflows reference repository names, filenames, and environment variables containing `jellyfin` (automation and repo-based conditions).
- `Directory.Packages.props` / `Directory.Build.props` — package IDs or project names containing `Jellyfin` (must not change).
- `.vscode/launch.json` and `.vscode/tasks.json` — run/build entries reference `jellyfin.dll` and default ffmpeg paths (tooling configs).
- `deployment/unraid/docker-templates/jellyfin.xml` — contains `Repository`, `Registry`, and GitHub/Template URLs that point to upstream jellyfin resources; these are intentionally preserved.
- `Emby.Server.Implementations/AppBase/BaseApplicationPaths.cs` — contains file/directory marker names like `.jellyfin-*` and temp/cache directories, which must remain for compatibility.
- Many `using Jellyfin.*;` and project/namespace references across `*.csproj` and source files — these are namespaces/assembly references and must not be renamed.

If you want me to prepare a second pass to rename any of the above categories, tell me which specific files or identifiers to change and I will create a targeted plan and PR with careful checks.

Generated on: 2026-05-12
