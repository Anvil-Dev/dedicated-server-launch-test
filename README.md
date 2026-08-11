# dedicated-server-launch-test: 1.21.6-forge

This exact-version branch is a compatibility wrapper around the `universal` branch. It runs the dedicated server launch test with Minecraft `1.21.6`, Forge, and Forge loader version `56.0.9`.

## Inputs

- `mods`: The paths to the mod files, one path per line. This is the recommended input.
- `mod`: Deprecated alias for `mods`. Use `mods` for new workflows.
- `extra-mods`: Path to extra mods (Modrinth `<id>:<version>` list).
- `maven-repos`: The path pointing to the Maven repositories (Direct `<url>` list).
- `maven-mods`: The path to the mod list file containing Maven coordinates (Maven `<group>:<project>:<version>` list).
- `url-mods`: The file path pointing to a list containing mod download URLs (Direct `<url>` list).
- `other-files`: The file path pointing to a list of URLs containing other resource files (Direct `<path>@<url>` list).
- `quiet-setup`: Whether server setup should be quiet (`true` or `false`). Defaults to `False`.

Either `mods` or the deprecated `mod` alias must be provided. All other inputs are optional.

## Example

```yaml
- name: Test mods on a dedicated server
  uses: Anvil-Dev/dedicated-server-launch-test@1.21.6-forge
  with:
    mods: |
      path/to/mod.jar
      path/to/another-mod.jar
    quiet-setup: "true"
```
