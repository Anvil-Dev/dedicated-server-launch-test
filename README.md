# dedicated-server-launch-test

Test if specified mods can launch on a dedicated server environment.

The `1.21.7-fabric` branch is an exact-version compatibility wrapper around the `universal` branch. It runs the universal action with Minecraft `1.21.7`, Fabric, and Fabric Loader `0.18.4`.

## Inputs

* `mods`: The paths to the mod files (one path per line). This is the recommended input.
* `mod`: Deprecated alias for `mods`.
* `extra-mods`: Path to extra mods (Modrinth `<id>:<version>` list).
* `maven-repos`: The path pointing to the Maven repositories (Direct `<url>` list).
* `maven-mods`: The path to the mod list file containing Maven coordinates (Maven `<group>:<project>:<version>` list).
* `url-mods`: The file path pointing to a list containing mod download URLs (Direct `<url>` list).
* `other-files`: The file path pointing to a list of URLs containing other resource files (Direct `<path>@<url>` list).
* `quiet-setup`: Should be quiet when setup servers (boolean, true/false). Defaults to `False`.

Either `mods` or the deprecated `mod` alias must be provided. Prefer `mods` for all new workflows.

## Example

```yaml
- name: Test dedicated server launch
  uses: Anvil-Dev/dedicated-server-launch-test@1.21.7-fabric
  with:
    mods: |
      path/to/mod.jar
      path/to/another-mod.jar
    extra-mods: |
      mod-id:mod-version
    maven-repos: |
      https://repo.example.com/releases
    maven-mods: |
      com.example:example-mod:1.0.0
    url-mods: |
      https://example.com/mod.jar
    other-files: |
      resources@https://example.com/resources.zip
    quiet-setup: "true"
```
