# AUR Packaging Notes

This project currently needs AUR packages for:
- `waybar-ai-usage` (main package)
- `python-json-five` (dependency)
- `libcurl-impersonate-bin` (provides `libcurl-impersonate`)
- `python-browser-cookie3` (already in AUR)
- `python-curl-cffi-git` (currently only git package in AUR)

## Build / Update

1) Update versions and checksums in each `PKGBUILD`.
2) Generate `.SRCINFO` in each package directory:
   ```bash
   makepkg --printsrcinfo > .SRCINFO
   ```
3) Push each package to its AUR git repo.

## GitHub Sources

- https://github.com/NihilDigit/python-json-five
- https://github.com/NihilDigit/libcurl-impersonate-bin

## Notes
- `setup`/`cleanup` rewrite `config.jsonc` (formatting/comments may change); backups are created.
- The AUR package shows a reminder in install/remove hooks to run `waybar-ai-usage cleanup` before uninstall.
- If a stable `python-curl-cffi` package appears in repos or AUR, replace `python-curl-cffi-git` dependency.
