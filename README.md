# dedicated-server-launch-test

Test if specified mods can launch on a dedicated server environment.

The `26.1.2-fabric` branch is a universal compatibility wrapper around the `universal` branch. It runs the universal action with Minecraft `26.1.2`, Fabric loader `0.19.3`, and the `fabric` loader type.

## Inputs

- `mods` (recommended): The paths to the mod files, one path per line.
- `mod` (deprecated): Alias for `mods`. Use `mods` for new workflows.
- `extra-mods`: Path to extra mods (Modrinth `<id>:<version>` list).
- `maven-repos`: The path pointing to the Maven repositories (Direct `<url>` list).
- `maven-mods`: The path to the mod list file containing Maven coordinates (Maven `<group>:<project>:<version>` list).
- `url-mods`: The file path pointing to a list containing mod download URLs (Direct `<url>` list).
- `other-files`: The file path pointing to a list of URLs containing other resource files (Direct `<path>@<url>` list).
- `quiet-setup`: Should be quiet when setup servers (`true`/`false`). Defaults to `False`.

At least one of `mods` or the deprecated `mod` alias must be provided. All other inputs are optional.

## Example

```yaml
steps:
  - name: Test dedicated server launch
    uses: Anvil-Dev/dedicated-server-launch-test@26.1.2-fabric
    with:
      mods: |
        path/to/mod.jar
      quiet-setup: "true"
```
