# LAN Server Properties
For Minecraft 1.12–1.16, and Forge.

When this mod is installed, it enhances the vanilla Minecraft "Open to LAN" screen, which now also:
* Allows for a port customization
* Allows a user to disable the online mode, so that also unauthenticated players can join the LAN server.

## For developers
To modify and debug the code, first import the repo as a Gradle project in Eclipse IDE, and then run the ForgeGradle task `genEclipseRuns`.

### Compile Fabric artifact
```
git clone git@github.com:rikka0w0/yarnforge-plugin.git
cd LanServerProperties
./gradlew build
```

### Compile Forge artifact
```
git clone git@github.com:rikka0w0/yarnforge-plugin.git
cd LanServerProperties
pushd forge
../gradlew userRemapYarn --mappings net.fabricmc:yarn:1.16.2+build.47 --mc-version 1.16.2 --no-daemon --stacktrace --debug
popd
./gradlew migrateMappings --mappings rikka:obf2mcp --input src/main/java --output forge/src/main/java
pushd forge
../gradlew build
popd
```