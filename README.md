# tips

## JPG or PNG to PDF

```
convert file.JPG -rotate "90>" -page a4 -density 150 file.pdf
```

## Mov to gif

```
#Create Gif from mov
# https://gist.github.com/tskaggs/6394639

mkdir tmp
ffmpeg -i test_video.mov -vf scale=320:-1 -r 10 tmp/ffout%3d.png
convert -delay 8 -loop 0 -resize 200x200\> tmp/ffout*.png animation.gif
rm -r tmp
```

## PNG remove alpha channel
```
convert demo.png -background "#FFFFFF" -alpha remove demo-white.png
```

## PNG change color, keep alpha channel
```
convert dog.png -fill red -colorize 100% dog-red.png
```

## PNG change color, remove alpha channel
```
convert dog.png -fill red -colorize 100% -background blue -alpha remove dog-red-blue.png
```

