# dedicated-server-launch-test

Test if specified mods can launch in a dedicated server environment.

The `1.15.2-fabric` branch is a compatibility wrapper around the `universal` branch. It supplies the fixed Minecraft version `1.15.2`, mod loader `fabric`, and loader version `0.18.4` while forwarding the inputs below.

## Inputs

- `mods`: The paths to the mod files, one path per line. This is the recommended input.
- `mod`: Deprecated alias for `mods`. Use `mods` for new workflows.
- `extra-mods`: Path to extra mods (Modrinth `<id>:<version>` list).
- `maven-repos`: The path pointing to the Maven repositories (Direct `<url>` list).
- `maven-mods`: The path to the mod list file containing Maven coordinates (Maven `<group>:<project>:<version>` list).
- `url-mods`: The file path pointing to a list containing mod download URLs (Direct `<url>` list).
- `other-files`: The file path pointing to a list of URLs containing other resource files (Direct `<path>@<url>` list).
- `quiet-setup`: Should be quiet when setup servers (boolean, `true`/`false`). Defaults to `False`.

Either `mods` or the deprecated `mod` alias must be provided. All other inputs are optional.

## Example

```yaml
- name: Test mod on a dedicated server
  uses: Anvil-Dev/dedicated-server-launch-test@1.15.2-fabric
  with:
    mods: |
      path/to/mod.jar
    quiet-setup: "true"
```
