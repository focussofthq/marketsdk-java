# Releasing

Publishing is by hand, from a clean clone at the tag, to Maven Central through the Central Portal.
The coordinates and version in `build.gradle` are stamped by the generator; nothing here is edited.

One-time setup:

1. A Central Portal account at https://central.sonatype.com, with the `com.marketsdk` namespace
   verified by the DNS TXT record the portal asks for on marketsdk.com.
2. A GPG key whose public key is on a key server (`gpg --keyserver keyserver.ubuntu.com --send-keys <id>`).

Each release, build and sign locally, then upload the bundle:

```bash
# Publish into a local directory laid out as a Maven repository.
MAVEN_PUBLISH_REGISTRY_URL=file://$PWD/staging MAVEN_USERNAME=x MAVEN_PASSWORD=x ./gradlew publish
# Sign every artifact.
cd staging && find . -type f ! -name '*.asc' ! -name '*.md5' ! -name '*.sha1' -exec gpg --armor --detach-sign {} ;
# Bundle, keeping the directory layout.
zip -r ../marketsdk-java-1.0.0-bundle.zip .
```

Upload the bundle at https://central.sonatype.com/publishing, check the validation result, and
publish. Then check https://central.sonatype.com/artifact/com.marketsdk/marketsdk-java.
