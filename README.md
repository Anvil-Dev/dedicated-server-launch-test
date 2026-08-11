# dedicated-server-launch-test

Test if specified mods can launch on dedicated server environment.

The `1.19.4-forge` branch is an exact-version compatibility wrapper around the `universal` branch. It fixes Minecraft to `1.19.4`, the mod loader to `forge`, and the loader version to `45.4.0`, then forwards the inputs below to the universal action.

## Inputs

- `mods` (recommended): The paths to the mod files, one path per line.
- `mod` (deprecated): Alias for `mods`. Use `mods` in new and updated workflows.
- `extra-mods`: Path to extra mods (Modrinth `<id>:<version>` list).
- `maven-repos`: The path pointing to the Maven repositories (Direct `<url>` list).
- `maven-mods`: The path to the mod list file containing Maven coordinates (Maven `<group>:<project>:<version>` list).
- `url-mods`: The file path pointing to a list containing mod download URLs (Direct `<url>` list).
- `other-files`: The file path pointing to a list of URLs containing other resource files (Direct `<path>@<url>` list).
- `quiet-setup`: Should be quiet when setup servers (boolean, `true`/`false`). Defaults to `False`.

At least one of `mods` or the deprecated `mod` alias must be provided.

## Example

```yaml
- name: Test dedicated server launch
  uses: Anvil-Dev/dedicated-server-launch-test@1.19.4-forge
  with:
    mods: |
      path/to/mod.jar
    quiet-setup: "true"
```
