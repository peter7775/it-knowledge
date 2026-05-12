

## Chromecast streaming z možností přerušení
`mkchromecast --video -i Druhá\ strana\ naděje_Toivon\ tuolla\ puolen\ \(2017\)\ by\ PanTosi.mkv --encoder-backend ffmpeg --control`

## html kontrola přehrávání
http://192.168.1.105:5000
## překódování videa
`ffmpeg -i Druhá\ strana\ naděje_Toivon\ tuolla\ puolen\ \(2017\)\ by\ PanTosi.mkv -c:v libx264 -c:a aac -preset ultrafast -f mp4 Druha_strana_nadeje.mp4`

## streamování s překódováním v reálném čase
`mkchromecast --video -i "Třinácté Patro.avi" --encoder-backend ffmpeg --command "ffmpeg -i INPUT -c:v libx264 -preset ultrafast -c:a aac -f mp4 pipe:1"`