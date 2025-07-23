I subscribed to Spotify for about 10 years, it was cool and convenient. I could remotely set my PlayStation 3 to play practically any music I wanted to listen to from my mobile phone!

But... I noticed that sometimes music that was once available to me was then region locked or completely removed from the platform. I read that artists on Spotify barely see any revenue from people listening to their music (however I do accept that I have found music I may have never heard through the suggested artists algorithm, which is fantastic imo, I created a python script to extract a users spotify playlists [here](https://github.com/albertoNilWisdom/spotify_playlist_tracks_to_CSV/blob/main/spotify_track_listing.py))

Considering the money I had spent on Spotify, roughly £1078.80 over ten years, I decided on self hosting my music library from my home server using the music I own.

Turning this:
![CDRACK](https://64.media.tumblr.com/b3106d81605f0731109e4e3ad71a6c1a/58e2845f74b4486a-2b/s1280x1920/28fd670ad11efbf515efc226431bef793db2b835.png)
Into this:

![library](https://64.media.tumblr.com/14819e0987074bd3b39f6ea1fad5303f/58e2845f74b4486a-44/s400x600/bdd9462ea37f9e52128e604e027f8b7ad07a481c.gif)

The tools I have used to set this up are:
- [debian](https://www.debian.org/)
- a ThinkCentre M720q Tiny computer
- [WireGuard](https://en.wikipedia.org/wiki/WireGuard)
- [a cloud hosted vps (virtual private server)](https://en.wikipedia.org/wiki/Virtual_private_server)
- [Jellyfin](https://jellyfin.org/)
- [Finamp](https://github.com/jmshrv/finamp)
- [Sound Juicer](https://en.wikipedia.org/wiki/Sound_Juicer)

To start, I needed a machine to store my media so I used a second hand ThinkCentre Tiny PC. This PC uses very little electricity which is great as it's switched on 24/7.

I installed Jellyfin on that machine to index, organise and manage the music. 

I've then used Finamp on my mobile devices to stream the media in my own home, it works great... when I am at home... 

As I extract all media from the CD's using Sound Juicer in a lossless format ([flac](https://en.wikipedia.org/wiki/FLAC)) the files themselves are very large, compared to mp3. 

Finamp allows you to download those files to your device to be played offline, should you choose. Unfortunately doing so would fill up a mobile device very quickly and I wanted to stream whatever music I wanted from outside of my house. 

This is where WireGuard comes in. I provisioned a virtual private server (VPS) that costs me about £2 per month to run, the sole purpose of this machine is to provide a VPN tunnel through to my media server, so it only needed 1 CPU core and 1GB of ram.

My mobile device connects to this WireGuard Virtual Private Network and then Jellyfin serves Finamp the media, over an encrypted tunnel on the internet.

Thankfully Jellyfin will transcode those large flac files on demand when you stream a media file to a device. so I don't run out of mobile data on my mobile phone contract when I am out of the house. This setting can be configured in the Finamp application settings on the client device.

Hopefully this might spark some interest to anyone reading and may get you to tinker with self hosting your own media too!

Cheers,
T

#wireguard #spofiy #jellyfin #media
