# dedicated-server-launch-test

This exact-version branch is a compatibility wrapper around the `universal` branch. It runs the universal dedicated server launch test with Minecraft `1.18.2`, the `forge` mod loader, and Forge loader version `40.3.12`.

## Inputs

- `mods`: The paths to the mod files, one path per line. This is the recommended input. Either `mods` or `mod` must be provided.
- `mod`: Deprecated alias for `mods`.
- `extra-mods`: Path to extra mods (Modrinth `<id>:<version>` list).
- `maven-repos`: The path pointing to the Maven repositories (Direct `<url>` list).
- `maven-mods`: The path to the mod list file containing Maven coordinates (Maven `<group>:<project>:<version>` list).
- `url-mods`: The file path pointing to a list containing mod download URLs (Direct `<url>` list).
- `other-files`: The file path pointing to a list of URLs containing other resource files (Direct `<path>@<url>` list).
- `quiet-setup`: Should be quiet when setup servers (`true`/`false`). Defaults to `False`.

## Example

```yaml
- name: Test dedicated server launch
  uses: Anvil-Dev/dedicated-server-launch-test@1.18.2-forge
  with:
    mods: |
      path/to/mod.jar
    quiet-setup: "true"
```
