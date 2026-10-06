# Releasing

Publishing is by hand, from a clean clone at the tag, to Maven Central through the Central Portal.
The coordinates and version in `build.gradle` are stamped by the generator; nothing here is edited.

One-time setup:

1. A Central Portal account at https://central.sonatype.com, with the `com.marketsdk` namespace
   verified by the DNS TXT record the portal asks for on marketsdk.com.
2. A GPG key whose public key is on a key server (`gpg --keyserver keyserver.ubuntu.com --send-keys <id>`).

Each release, build into the local Maven repository, then sign, checksum, and bundle outside the
clone. The generated build's publish repository carries credentials, which Gradle refuses for a
`file://` URL, so `publishToMavenLocal` is the route.

```bash
./gradlew publishToMavenLocal
V=1.0.0
B=$(mktemp -d)/bundle && D=$B/com/marketsdk/marketsdk-java/$V && mkdir -p $D
cp ~/.m2/repository/com/marketsdk/marketsdk-java/$V/marketsdk-java-$V{.jar,.pom,.module,-sources.jar,-javadoc.jar} $D/
cd $D && for f in *; do gpg --armor --detach-sign "$f"; md5 -q "$f" > "$f.md5"; shasum -a 1 "$f" | cut -d' ' -f1 > "$f.sha1"; done
cd $B && zip -qr ~/marketsdk-java-$V-bundle.zip com && echo ~/marketsdk-java-$V-bundle.zip
```

Upload the bundle at https://central.sonatype.com/publishing, check the validation result, and
publish. Then check https://central.sonatype.com/artifact/com.marketsdk/marketsdk-java.
