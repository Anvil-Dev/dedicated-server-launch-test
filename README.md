# Dedicated Server Launch Test

This exact-version branch is a compatibility wrapper around the `universal` branch. It runs the universal dedicated server launch test with this fixed configuration:

- Minecraft version: `1.14.4`
- Mod loader: `fabric`
- Loader version: `0.18.4`

## Inputs

- `mods` (recommended): The paths to the mod files (one path per line).
- `mod` (deprecated): Deprecated alias for `mods`.
- `extra-mods`: Path to extra mods (Modrinth `<id>:<version>` list).
- `maven-repos`: The path pointing to the Maven repositories (Direct `<url>` list).
- `maven-mods`: The path to the mod list file containing Maven coordinates (Maven `<group>:<project>:<version>` list).
- `url-mods`: The file path pointing to a list containing mod download URLs (Direct `<url>` list).
- `other-files`: The file path pointing to a list of URLs containing other resource files (Direct `<path>@<url>` list).
- `quiet-setup`: Should be quiet when setup servers (boolean, true/false). Defaults to `False`.

Provide either `mods` or the deprecated `mod` alias. New workflows should use `mods`.

## Example

```yaml
- name: Test dedicated server launch
  uses: Anvil-Dev/dedicated-server-launch-test@1.14.4-fabric
  continue-on-error: false
  with:
    mods: |
      path/to/mod.jar
    quiet-setup: "true"
```
