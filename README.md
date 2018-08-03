# NginxVideo
Dockerfile for serving streaming video from nginx

uses the nginx -rtmp file

Based on Blog here:

From https://www.leaseweb.com/labs/2013/11/streaming-video-demand-nginx-rtmp-module/

##Dockerhub
The build is automaticaly built to docker hub here:

https://hub.docker.com/r/acobley/nginxvideo/


##Usage:

docker build radioafricagroup/devops:nginxvideoserv .

docker run -d -p 1935:1935 -p 8060:80 --name videoserv -v $PWD/mp4:/var/mp4s  -v $PWD/www:/var/www radioafricagroup/devops:nginxvideoserv /usr/local/nginx-streaming/sbin/nginx

Expects mp4 files in the mp4 directory

Expects html and graphics in www/html directory

video stats are in 127.0.0.1:8060/stats

##How to test videos

// test using the vlc console N.B change the 127.0.0.1 to suite yout server public ip

rtmp://127.0.0.1:1935/vod2/City_Boy_[Bawazir]_-_Bad_Gyal_(Official_4K_Video).mp4
rtmp://127.0.0.1:1935/vod2/Davido_-_Dengeme_Ft._Stunnah_Gee_(Official_Video).mp4
rtmp://127.0.0.1:1935/vod2/Diplo,_French_Montana_&_Lil_Pump_ft._Zhavia_-_Welcome_To_The_Party_(Official_Vid_1.mp4
rtmp://127.0.0.1:1935/vod2/Dobre_Brothers_-_Stop_That_(Music_Video).mp4
rtmp://127.0.0.1:1935/vod2/Falz_-_Next_(Official_Video)_ft._Maleek_Berry,_MEDIKAL.mp4
rtmp://127.0.0.1:1935/vod2/Jason_Mraz_-_Might_As_Well_Dance_[Official_Video].mp4
rtmp://127.0.0.1:1935/vod2/Jax_Jones,_Mabel_-_Ring_Ring_(Official_Video)_ft._Rich_The_Kid.mp4
rtmp://127.0.0.1:1935/vod2/Kelechi_Africana_ft_Dj_2one2_-_Wapoteze_(official_video).mp4
rtmp://127.0.0.1:1935/vod2/Khalid_-_OTW_(Official_Video)_ft._6LACK,_Ty_Dolla_$ign.mp4
rtmp://127.0.0.1:1935/vod2/Lary_Over_-_Sola_[Official_Video].mp4
rtmp://127.0.0.1:1935/vod2/Lil_Pump_-_Drug_Addicts_(Official_Music_Video).mp4
rtmp://127.0.0.1:1935/vod2/Nadia_Mukami_-_African_Lover_(Official_Video).mp4
rtmp://127.0.0.1:1935/vod2/Nicki-Minaj-Bed-feat-Ariana-Grande.mp4
rtmp://127.0.0.1:1935/vod2/sample.mp4
rtmp://127.0.0.1:1935/vod2/Swae_Lee,_Slim_Jxmmi,_Rae_Sremmurd_-_Guatemala.mp4
rtmp://127.0.0.1:1935/vod2/Tekno-One-Shot-ft-Steven-C.mp4
rtmp://127.0.0.1:1935/vod2/Tom_Zanetti_-_Make_It_Look_Good_(Official_Video)_ft._Preditah.mp4
rtmp://127.0.0.1:1935/vod2/Tory_Lanez,_Ozuna_-_Pa_Mi.mp4
rtmp://127.0.0.1:1935/vod2/YK_Osiris_-_Timing.mp4
rtmp://127.0.0.1:1935/vod2/ZIKKI_ft_TARRUS_RILEY_-_KAMATA_(OFFICIAL_VIDEO).mp4




// test  videos using your terminal and vlcgit status

sudo apt-get install rtmpdump

rtmpdump -v -r "rtmp://127.0.0.1:1935/vod2/City_Boy_[Bawazir]_-_Bad_Gyal_(Official_4K_Video).mp4" -o - | "vlc" -
rtmpdump -v -r "rtmp://127.0.0.1:1935/vod2/Davido_-_Dengeme_Ft._Stunnah_Gee_(Official_Video).mp4" -o - | "vlc" -
rtmpdump -v -r "rtmp://127.0.0.1:1935/vod2/Diplo,_French_Montana_&_Lil_Pump_ft._Zhavia_-_Welcome_To_The_Party_(Official_Vid_1.mp4" -o - | "vlc" -
rtmpdump -v -r "rtmp://127.0.0.1:1935/vod2/Dobre_Brothers_-_Stop_That_(Music_Video).mp4" -o - | "vlc" -
rtmpdump -v -r "rtmp://127.0.0.1:1935/vod2/Falz_-_Next_(Official_Video)_ft._Maleek_Berry,_MEDIKAL.mp4" -o - | "vlc" -
rtmpdump -v -r "rtmp://127.0.0.1:1935/vod2/Jason_Mraz_-_Might_As_Well_Dance_[Official_Video].mp4" -o - | "vlc" -
rtmpdump -v -r "rtmp://127.0.0.1:1935/vod2/Jax_Jones,_Mabel_-_Ring_Ring_(Official_Video)_ft._Rich_The_Kid.mp4" -o - | "vlc" -
rtmpdump -v -r "rtmp://127.0.0.1:1935/vod2/Kelechi_Africana_ft_Dj_2one2_-_Wapoteze_(official_video).mp4" -o - | "vlc" -
rtmpdump -v -r "rtmp://127.0.0.1:1935/vod2/Khalid_-_OTW_(Official_Video)_ft._6LACK,_Ty_Dolla_$ign.mp4" -o - | "vlc" -
rtmpdump -v -r "rtmp://127.0.0.1:1935/vod2/Lary_Over_-_Sola_[Official_Video].mp4" -o - | "vlc" -
rtmpdump -v -r "rtmp://127.0.0.1:1935/vod2/Lil_Pump_-_Drug_Addicts_(Official_Music_Video).mp4" -o - | "vlc" -
rtmpdump -v -r "rtmp://127.0.0.1:1935/vod2/Nadia_Mukami_-_African_Lover_(Official_Video).mp4" -o - | "vlc" -
rtmpdump -v -r "rtmp://127.0.0.1:1935/vod2/Nicki-Minaj-Bed-feat-Ariana-Grande.mp4" -o - | "vlc" -
rtmpdump -v -r "rtmp://127.0.0.1:1935/vod2/sample.mp4" -o - | "vlc" -
rtmpdump -v -r "rtmp://127.0.0.1:1935/vod2/Swae_Lee,_Slim_Jxmmi,_Rae_Sremmurd_-_Guatemala.mp4" -o - | "vlc" -
rtmpdump -v -r "rtmp://127.0.0.1:1935/vod2/Tekno-One-Shot-ft-Steven-C.mp4" -o - | "vlc" -
rtmpdump -v -r "rtmp://127.0.0.1:1935/vod2/Tom_Zanetti_-_Make_It_Look_Good_(Official_Video)_ft._Preditah.mp4" -o - | "vlc" -
rtmpdump -v -r "rtmp://127.0.0.1:1935/vod2/Tory_Lanez,_Ozuna_-_Pa_Mi.mp4" -o - | "vlc" -
rtmpdump -v -r "rtmp://127.0.0.1:1935/vod2/YK_Osiris_-_Timing.mp4" -o - | "vlc" -
rtmpdump -v -r "rtmp://127.0.0.1:1935/vod2/ZIKKI_ft_TARRUS_RILEY_-_KAMATA_(OFFICIAL_VIDEO).mp4" -o - | "vlc" -



