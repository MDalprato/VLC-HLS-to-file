# VLC-HLS-to-file
Download HLS stream to file with VLC

In order to save an HLS stream (m3u8) to a file with VLC using command line is necessary to follow this scheme:

vlc_path "m3u8 url" --sout=#transcode{vcodec=h264,acodec=mpga,ab=128,channels=2,samplerate=44100}:std{access=file{no-overwrite},mux=mp4,dst='D:/pech/s1e0.mp4'} vlc://quit

where:

vlc_path: is the path of VLC
m3u8 url: is you HLS file link
transcode{vcodec=h264,acodec=mpga,ab=128,channels=2,samplerate=44100}: are the VLC settings for the output file
D:/pech/s1e0.mp4 = is the path for the output file
vlc://quit = is not mandatory, but if you are lunching more then one command is a must in order to close at the end of every job.
 
Example:

"C:\Program Files\VideoLAN\VLC\vlc.exe" "https://2uscreativem3-vh.akamaihd.net/i/archive_e/Archive/raidue/1241333.mp4/index_0_av.m3u8" --sout=#transcode{vcodec=h264,acodec=mpga,ab=128,channels=2,samplerate=44100}:std{access=file{no-overwrite},mux=mp4,dst='D:/pech/s1e0.mp4'} vlc://quit
