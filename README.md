# dedicated-server-launch-test
Test if specified mods can launch on dedicated server environment

## Inputs

* mod: Path to the main mod file (required field)
* extra-mods: Path to extra mods (Modrinth `<id>:<version>` list)
* maven-repos: The path pointing to the Maven repositories (Direct `<url>` list)
* maven-mods: The path to the mod list file containing Maven coordinates (Maven `<group>:<project>:<version>` list)
* url-mods: The file path pointing to a list containing mod download URLs (Direct `<url>` list)
* other-files: The file path pointing to a list of URLs containing other resource files (Direct `<path>@<url>` list)

### Example
```yaml
  - name: gametest
    uses: Anvil-Dev/dedicated-server-launch-test@1.21.1-neoforge
    continue-on-error: false
    with:
      mod: mods/anvilcraft-neoforge-1.21.1-1.5.0.jar
      extra-mods: |
        create:mc1.21.1-6.0.9
        patchouli:1.21.1-92-neoforge
      maven-repos: |
        https://server.cjsah.net:1002/maven
        https://maven.createmod.net
      maven-mods: |
        dev.anvilcraft.lib:anvillib-neoforge-1.21.1:1.4.0+build.172
        net.createmod.ponder:Ponder-NeoForge-1.21.1
      url-mods: |
        https://maven.latvian.dev/releases/dev/latvian/mods/rhino-neoforge/2006.2.4-build.17/rhino-neoforge-2006.2.4-build.17.jar
        https://maven.latvian.dev/releases/dev/latvian/mods/kubejs-neoforge/2101.7.2-build.351/kubejs-neoforge-2101.7.2-build.351.jar
      other-files: |
        resources@https://cdn.modrinth.com/data/MoyjiexA/versions/Kf4o6AQb/Strong%20male%20basic%20color.zip
```
