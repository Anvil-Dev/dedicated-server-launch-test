# dedicated-server-launch-test

Test if specified mods can launch in a dedicated server environment.

The `1.21.5-forge` branch is an exact-version compatibility wrapper around the `universal` branch. It delegates the test with Minecraft `1.21.5`, Forge, and Forge loader version `55.1.4` fixed for compatibility.

## Inputs

- `mods`: The paths to the mod files, one path per line. This is the recommended input.
- `mod`: Deprecated alias for `mods`. Use `mods` for new workflows.
- `extra-mods`: Path to extra mods (Modrinth `<id>:<version>` list).
- `maven-repos`: The path pointing to the Maven repositories (Direct `<url>` list).
- `maven-mods`: The path to the mod list file containing Maven coordinates (Maven `<group>:<project>:<version>` list).
- `url-mods`: The file path pointing to a list containing mod download URLs (Direct `<url>` list).
- `other-files`: The file path pointing to a list of URLs containing other resource files (Direct `<path>@<url>` list).
- `quiet-setup`: Whether server setup should be quiet (`true` or `false`). Defaults to `False`.

At least one of `mods` or the deprecated `mod` alias must be provided.

## Example

```yaml
- name: Test dedicated server launch
  uses: Anvil-Dev/dedicated-server-launch-test@1.21.5-forge
  with:
    mods: |
      path/to/mod.jar
    quiet-setup: "true"
```
