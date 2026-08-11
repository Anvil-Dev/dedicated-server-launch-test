# dedicated-server-launch-test

This exact-version branch is a compatibility wrapper around the `universal` branch. It runs the universal dedicated server launch test with Minecraft `1.21.1`, the `neoforge` mod loader, and NeoForge `21.1.217`.

## Inputs

One of `mods` or `mod` must be provided. Prefer `mods`; `mod` is retained only as a deprecated compatibility alias.

- `mods`: The paths to the mod files (one path per line).
- `mod`: Deprecated alias for `mods`.
- `extra-mods`: Path to extra mods (Modrinth `<id>:<version>` list).
- `maven-repos`: The path pointing to the Maven repositories (Direct `<url>` list).
- `maven-mods`: The path to the mod list file containing Maven coordinates (Maven `<group>:<project>:<version>` list).
- `url-mods`: The file path pointing to a list containing mod download URLs (Direct `<url>` list).
- `other-files`: The file path pointing to a list of URLs containing other resource files (Direct `<path>@<url>` list).
- `quiet-setup`: Should be quiet when setup servers (boolean, true/false). Defaults to `"False"`.

## Example

```yaml
- name: Test dedicated server launch
  uses: Anvil-Dev/dedicated-server-launch-test@1.21.1-neoforge
  with:
    mods: |
      path/to/mod.jar
    quiet-setup: "true"
```
