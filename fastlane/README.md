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
vim fastlane.deliver.download_metadata.sh

```
#! /bin/sh
fastlane deliver download_metadata \
--metadata_path "fastlane/metadata" \
--app_identifier "com.your.app" \
--username "xxx@gmail.com" \
--team_id "teamid"
\

```

## Download screenshots

Change the line --use-live-version to false if there is no live version.

```
vim fastlane.deliver.download_screenshots.sh
```

```
#! /bin/sh

fastlane deliver download_screenshots \
--use_live_version true 
--screenshot_path "fastlane/screnshot_itc" \
--app_identifier "com.sm4rtapp.scan.warehouse" \
--username "djabolo@gmail.com" \
--team_id "117904455"
\
```


## Download screenshots

```
fastlane deliver download_screenshots --use_live_version true -a "com.your.app"
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

### Keyword sans title

Framefile.json

```
 "data": [
        {
            "filter": "1-Sim",
            "show_complete_frame": true,
            "keyword": {
                "color": "#d21559"
            },
            "title": {
            	   "color": "#FFFFFF01"
            	   "text": "."
            },
            "stack_title" : false
        },
```

### Erreur sur les frame d'iPad 3rd generation

https://github.com/fastlane/frameit-frames/issues/7

* Download metadata from itunes connect : fastlane.deliver.download_metadata.sh
* Download screenshots from itunes connect : fastlane deliver download_screenshots
