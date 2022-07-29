# SPIKE for tool swift-api-digester

## How to generete json file for current version API - frameworks:

`xcrun --sdk iphonesimulator /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/swift-api-digester \
-module TomTomSDKCommon \
-dump-sdk \
-I /Users/tom/Library/Developer/Xcode/DerivedData/GoSDK-dkxziqaaipgkurgwauiqijosuqht/Build/Products/Debug-iphonesimulator/TomTomSDKCommon.framework/Modules \  
-target arm64-apple-ios-simulator -output-dir current/. `

## How to compare json files with the result

`xcrun /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/bin/swift-api-digester -diagnose-sdk --input-paths API/iphoneos.json --input-paths current/API/iphoneos.json -v`

## How looks like diff verions of frameworks:

Please take a look on file `result.txt`
