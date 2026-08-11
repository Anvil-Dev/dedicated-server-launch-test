# dedicated-server-launch-test

Test if specified mods can launch on dedicated server environment.

The `1.21.10-forge` branch is an exact-version compatibility wrapper around the `universal` branch. It runs Minecraft `1.21.10` with Forge `60.1.5` while forwarding all supported inputs to the universal action.

## Inputs

- `mods`: The paths to the mod files (one path per line). This is the recommended input.
- `mod`: Deprecated alias for `mods`.
- `extra-mods`: Path to extra mods (Modrinth `<id>:<version>` list).
- `maven-repos`: The path pointing to the Maven repositories (Direct `<url>` list).
- `maven-mods`: The path to the mod list file containing Maven coordinates (Maven `<group>:<project>:<version>` list).
- `url-mods`: The file path pointing to a list containing mod download URLs (Direct `<url>` list).
- `other-files`: The file path pointing to a list of URLs containing other resource files (Direct `<path>@<url>` list).
- `quiet-setup`: Should be quiet when setup servers (boolean, true/false). Defaults to `False`.

Use `mods` for new workflows. The singular `mod` input remains available only as a deprecated compatibility alias.

## Example

```yaml
- name: Test dedicated server launch
  uses: Anvil-Dev/dedicated-server-launch-test@1.21.10-forge
  with:
    mods: |
      path/to/mod.jar
    quiet-setup: "true"
```
