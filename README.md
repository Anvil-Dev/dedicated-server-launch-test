# dedicated-server-launch-test

Test if specified mods can launch in a dedicated server environment.

The `1.21.9-neoforge` branch is a compatibility wrapper around the `universal` branch. It runs the universal action with Minecraft `1.21.9`, NeoForge, and loader version `21.9.16-beta`.

## Inputs

- `mods`: The paths to the mod files, one path per line. This is the recommended input. Either `mods` or `mod` must be provided.
- `mod`: Deprecated alias for `mods`. Use `mods` for new workflows.
- `extra-mods`: Path to extra mods (Modrinth `<id>:<version>` list).
- `maven-repos`: The path pointing to the Maven repositories (Direct `<url>` list).
- `maven-mods`: The path to the mod list file containing Maven coordinates (Maven `<group>:<project>:<version>` list).
- `url-mods`: The file path pointing to a list containing mod download URLs (Direct `<url>` list).
- `other-files`: The file path pointing to a list of URLs containing other resource files (Direct `<path>@<url>` list).
- `quiet-setup`: Whether server setup should be quiet (`true`/`false`). Defaults to `False`.

## Example

```yaml
- name: Test mods on a dedicated server
  uses: Anvil-Dev/dedicated-server-launch-test@1.21.9-neoforge
  with:
    mods: |
      path/to/mod.jar
    quiet-setup: "true"
```
