# Fastlane
## Fastlane version
2.70.1
## Get your fastlane version :
```
fastlane -v
```
## Fastlane - XCodebuild
Got to Xcode -> Preferences -> Locations -> Command Line Tools

## Download metadata
fastlane.deliver.download_metadata.sh
```
fastlane deliver download_metadata \
-m "fastlane/metadata_audioquiz" \
-a "com.orvain.audioquizz.animal" \
-u "djabolo@gmail.com" \
-k "117904455" \
\
```

## Snapshot
### Build
In Fastfile
```
#desc Take the screenshots
lane :screenshot_audioquiz do
    snapshot(
    project: "quizz.xcodeproj",
    scheme: "fastlane.audioquizz",
    languages: ["en-US", "fr-FR", "de-DE","es-ES", "pt-BR", "ja", "zh-Hans"],
    devices: ["iPhone 6 Plus","iPhone Xs Max","iPad Pro (12.9-inch) (2nd generation)","iPad Pro (12.9-inch) (3rd generation)"],
    clear_previous_screenshots: true,
    output_directory: "fastlane/screenshots_audioquizz"
)
end
```

## Frameit

### Erreur sur les frame d'iPad 3rd generation

https://github.com/fastlane/frameit-frames/issues/7

* Download metadata from itunes connect : fastlane.deliver.download_metadata.sh
* Download screenshots from itunes connect : fastlane deliver download_screenshots
