# dedicated-server-launch-test

Test whether specified mods can launch in a dedicated server environment.

The `1.21.11-fabric` branch is an exact-version compatibility wrapper around the `universal` action. It runs the universal workflow with Minecraft `1.21.11`, Fabric, and Fabric Loader `0.18.4`.

## Inputs

- `mods`: The paths to the mod files (one path per line). This is the recommended input.
- `mod`: Deprecated alias for `mods`. Use `mods` for new workflows.
- `extra-mods`: Path to extra mods (Modrinth `<id>:<version>` list).
- `maven-repos`: The path pointing to the Maven repositories (Direct `<url>` list).
- `maven-mods`: The path to the mod list file containing Maven coordinates (Maven `<group>:<project>:<version>` list).
- `url-mods`: The file path pointing to a list containing mod download URLs (Direct `<url>` list).
- `other-files`: The file path pointing to a list of URLs containing other resource files (Direct `<path>@<url>` list).
- `quiet-setup`: Should be quiet when setup servers (boolean, `true`/`false`). Defaults to `False`.

Either `mods` or the deprecated `mod` alias must be provided.

## Example

```yaml
- name: Test mod on a dedicated server
  uses: Anvil-Dev/dedicated-server-launch-test@1.21.11-fabric
  with:
    mods: |
      path/to/mod.jar
      path/to/another-mod.jar
    quiet-setup: "true"
```
