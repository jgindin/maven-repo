# maven-repo
Private maven repo for my projects

# How to Use
To create the artifacts for a project, add the following to the build.gradle:
```
ext {
    PUBLISH_GROUP_ID = 'com.gindin'
    PUBLISH_ARTIFACT_ID = 'material-seekbar-preference'
    PUBLISH_VERSION = '0.13'
}

apply from: 'https://raw.githubusercontent.com/blundell/release-android-library/master/android-release-aar.gradle'
```

(Obviously, set the PUBLISH_* values according to the project and release ;-)

Then, you can build and produce the artifacts with:
```
./gradlew clean build generateRelease
```

This will put the generated artifacts into the build/release/PUBLISH_VERSION/PUBLISH_GROUP_ID/PUBLISH_ARTIFACT_ID/PUBLISH_VERSION directory (except every part of the PUBLISH_GROUP_ID separated with a '.' will become a separate directory).

Assuming you've cloned this repository to ~/src/maven-repo:
```
cp -rp build/release/PUBLISH_VERSION ~/src/maven-repo
hg add
hg commit
hg push
```
(Replace 'hg' with 'git' as necessary.)
