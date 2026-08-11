# dedicated-server-launch-test

Test if specified mods can launch in a dedicated server environment.

The `1.21.10-fabric` branch is an exact-version compatibility wrapper around the `universal` branch. It runs the universal action with Minecraft `1.21.10`, Fabric, and Fabric Loader `0.18.4`.

## Inputs

- `mods`: The paths to the mod files, one path per line. This is the recommended input.
- `mod`: Deprecated alias for `mods`. Use `mods` for new workflows.
- `extra-mods`: Path to extra mods (Modrinth `<id>:<version>` list).
- `maven-repos`: The path pointing to the Maven repositories (Direct `<url>` list).
- `maven-mods`: The path to the mod list file containing Maven coordinates (Maven `<group>:<project>:<version>` list).
- `url-mods`: The file path pointing to a list containing mod download URLs (Direct `<url>` list).
- `other-files`: The file path pointing to a list of URLs containing other resource files (Direct `<path>@<url>` list).
- `quiet-setup`: Whether server setup should be quiet (`true` or `false`). Defaults to `False`.

Either `mods` or the deprecated `mod` alias must be provided.

## Example

```yaml
- name: Test dedicated server launch
  uses: Anvil-Dev/dedicated-server-launch-test@1.21.10-fabric
  with:
    mods: |
      path/to/mod.jar
      path/to/another-mod.jar
    extra-mods: |
      example-mod:1.0.0
    maven-repos: |
      https://repo.example.com/releases
    maven-mods: |
      com.example:example-mod:1.0.0
    url-mods: |
      https://example.com/mods/example-mod.jar
    other-files: |
      config@https://example.com/config/server-config.zip
    quiet-setup: "true"
```
