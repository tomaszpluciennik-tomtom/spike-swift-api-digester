# SPIKE for the swift-api-digester tool.

## How to generate a file to describe the public API for a given SDK:

Below is the command we will use to get the metadata in json form for the TomTomSDKCommon.
With this command, we first generate json before the changes and after removing the method from `GeoLineSegment`, a second time in path` current / API`:

`xcrun --sdk iphonesimulator /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/swift-api-digester \
-module TomTomSDKCommon \
-dump-sdk \
-I /Users/tom/Library/Developer/Xcode/DerivedData/GoSDK-dkxziqaaipgkurgwauiqijosuqht/Build/Products/Debug-iphonesimulator/TomTomSDKCommon.framework/Modules \  
-target arm64-apple-ios-simulator -output-dir current/. `

## How to compare files generated with swift-api-digester:

To compare files use the following skypt which will generate a diff between the first and second versions of TomTomSDKCommon.

`xcrun /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/swift-api-digester -diagnose-sdk --input-paths API/iphoneos.json --input-paths current/API/iphoneos.json -v`

We can see the result in the file `result.txt`
