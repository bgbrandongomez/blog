---
title: Music Artistry
date: 2017-11-20 15:14:00
---

[flickr]: https://www.flickr.com/photos/senorcontento/
[question]: https://sound.stackexchange.com/questions/42340/how-to-cancel-out-sound-in-an-audio-track

[original]: /postdata/2017-11-20-Music-Artistry/audio/01%20-%20Siren%20(HID).flac
[original-2tracks]: /postdata/2017-11-20-Music-Artistry/audio/02%20-%20Siren.flac

[spectrogram-audacity]: /postdata/2017-11-20-Music-Artistry/images/Screenshot from 2017-11-16 17-02-37.png
[spectrogram-logf-audacity]: /postdata/2017-11-20-Music-Artistry/images/Screenshot from 2017-11-16 17-02-43.png

[amazon-mp3]: /postdata/2017-11-20-Music-Artistry/audio/B0777PYL9G_(disc_1)_01_-_Siren_(Hidden_Image_Demo)_(Demo).mp3
[gp-mp3]: /postdata/2017-11-20-Music-Artistry/audio/01 - Siren (Hidden Image Demo) (Demo).mp3

[original-tags-image]: /postdata/2017-11-20-Music-Artistry/images/Screenshot from 2017-11-16 17-47-25.png
[amazon-tags-image]: /postdata/2017-11-20-Music-Artistry/images/Screenshot from 2017-11-16 17-47-52.png
[google-play-tags-image]: /postdata/2017-11-20-Music-Artistry/images/Screenshot from 2017-11-16 17-47-30.png

[spectrogram-perl]: /postdata/2017-11-20-Music-Artistry/spectrogram.perl
[bsd-license]: http://web.archive.org/web/20120218224021/http://www.linfo.org:80/bsdlicense.html
[original-spectrogram-perl]: http://web.archive.org/web/20110208000943/http://devrand.org:8080/cgi-bin/cgit/imageSpectrogram/plain/imageSpectrogram.pl
[spectrogram-blog-post]: http://web.archive.org/web/20120224061437/http://devrand.org/view/imageSpectrogram

[48x48-audio]: /postdata/2017-11-20-Music-Artistry/audio/SenorContento-48x48.png.wav

[audacity-siren]: /postdata/2017-11-20-Music-Artistry/projects/Siren.aup.zip
[audacity-hidden-image-siren]: /postdata/2017-11-20-Music-Artistry/projects/HiddenAudioQuestion.aup.zip

[media-license]: https://creativecommons.org/licenses/by-sa/4.0/
[gpl-3-license]: https://www.gnu.org/licenses/gpl-3.0.en.html

Be warned, this is a very lengthy post as I am covering multiple topics in the Sound Adventures I have had when it comes from creating sound all the way to working with a record label. The post is split into sections by headers, such as the one right below that says "Musical Artistry", so it can be easier to read, understand, and even remember where you left off last time you read it (especially if you do not read this whole post in one sitting). Enjoy my post about my Sound Adventures!

### Musical Artistry

I want to share my art with the world. I have created several forms of art including digital images, which can be found on [Flickr][flickr], some paintings, sketches, and even random and obscure types of art (especially when it involves programming or untraditional tools or materials). The type I want to share in this post is digital audio. I have not made it to the point where I want to try to make music, but at least I can make sound files.

My current and only sound file is a siren. I used a sine wave generator and then told it to generate a clip in which the frequency dropped to zero as it got to half a second. I did the reverse from half a second to the full second. I then cut and paste the track every tenth of a second to be alternating between the left and right earbud (or speaker) and found it had this weird clicking sound. Turns out the clicking is produced by our brains when I don't gradually lower the volume (or amplitude) whenever I go to switch earbuds. The same for increasing the volume. So, I then went to the center of every alternation of the speaker and raised the volume until the halfway point then immediately lowered it again.

I had done this as I was bored and wanted to create something to challenge me a little bit. I ultimately had used this siren to hide an image inside the file because I was messing around with the idea of producing images with spectrograms. I couldn't upload a Beatles track to the internet, so I used my own creation. Then I asked the question about hiding audio in a sound file on [Stack Exchange][question]. While I still have not figured out how to perfectly hide audio (as noise cancellation only works if I can get the same exact frequency and amplitude of two polar opposite noises to hit the same speakers at the exact same time), I have managed to learn more about having three or more tracks in a sound file.

Having the ability to include this many tracks in my audio peaks my interest in wanting to learn how music could be different if artists spent some of their creativity into creating songs that could have a different part on three, four, or even six and ten speakers. This will require a special set up by the people who enjoy this music, but at least the software today can retain compatibility as it chooses which speakers to put the sound on by having the artist choose left, right, or mono for each track. The special setup will just allow the listener to either ignore completely or use these extra speakers in addition to the previous three options. Ignoring the three options, a user can say, speaker 1 goes to track 1, speaker 2 to track 2, 3 to 3 and so on. When used in addition to the three options, one could have speakers lined up in a room, 3 on the left side, 3 on right, and then choose the first speaker on both sides to be left and right and the remaining four can be tracks 3 through 6. Now, the issue of which speakers should play which track can easily be solved by metadata to help suggest to the player what setup would work. Now, obviously, the user should be able to override which tracks go to which speaker, especially since the artist will not know the exact setup of the users home (or work). How the speakers are chosen are more up to the user and software developer and not the artist. The artist just suggests which setup would work best for that piece.


### The Siren

I am going to use my siren as an example for this post. You can download the file from this [blog][original]. If you hear buzzing in the background, you likely have headphones on, are in your car, or otherwise have multiple speakers playing the sound file at once right now. If the audio sounds like [this][original-2tracks], then you are playing it on a single speaker. The second audio file is the exact same thing as the first one, but with tracks 3 and 4 removed to remove the hidden image.

This is the Siren with the hidden image:
<center>
<audio controls>
  <source src="/postdata/2017-11-20-Music-Artistry/audio/01%20-%20Siren%20(HID).flac" type="audio/flac">
  Your browser does not support the audio element.
</audio>
</center>

This is the Siren without the hidden image:
<center>
<audio controls>
  <source src="/postdata/2017-11-20-Music-Artistry/audio/02%20-%20Siren.flac" type="audio/flac">
  Your browser does not support the audio element.
</audio>
</center>

### The Problem

Being able to create music with many speakers is wonderful, until you realize their is a problem with the versions of the tracks that have been posted to the online stores such as Google Play Music, Amazon Music, and so on. Now, I have not contacted these companies about this issue, so I am not saying that they are unwilling to listen if people were to contact them about it. I am saying that there are problems with the audio file that ruin the experience for the person who buys the file. As an artist, had I never tested it myself, I would not have known.

The problem is that when the audio files are sent to the stores, all the tracks are merged into 2 tracks at some point in their journey. It could be merged by Distrokid as it is submitted to the stores, but it could also just simply be merged by the stores as they process it. I highly doubt it is Distrokid as I can still pull my original, unmodified flac file from their site, as seen in the picture below (you can click the images to open them in a new tab).

<!--Todo, go back and edit CSS to automatically make image tags use width 100%. That way, you can use markdown to "properly" size the images. Remember, that not all images are going to look right when squished. I say this in terms of, it is illegible-->

Distrokid site:
<a target="_blank" href="/postdata/2017-11-20-Music-Artistry/images/Screenshot from 2017-11-16 11-18-29.png"><image src="/postdata/2017-11-20-Music-Artistry/images/Screenshot from 2017-11-16 11-18-29.png" width="100%"></image></a>

You can see that download icon by the text that says "Siren (Hidden Image Demo)". It allows me to grab the original flac file as it was when I uploaded it. Now, what the tracks are supposed to look like in terms of spectrograms versus how they look on Amazon's mp3 are very different. To achieve the same types of images (especially if in Audacity), run the tracks under ["Spectrogram"][spectrogram-audacity] and not ["Spectrogram log(f)"][spectrogram-logf-audacity].

Original's Spectrogram produced by Sox:
<a target="_blank" href="/postdata/2017-11-20-Music-Artistry/images/01 - Siren (HID).png"><image src="/postdata/2017-11-20-Music-Artistry/images/01 - Siren (HID).png" width="100%"></image></a>

Amazon's Spectrogram produced by Sox:
<a target="_blank" href="/postdata/2017-11-20-Music-Artistry/images/B0777PYL9G_(disc_1)_01_-_Siren_(Hidden_Image_Demo)_(Demo).png"><image src="/postdata/2017-11-20-Music-Artistry/images/B0777PYL9G_(disc_1)_01_-_Siren_(Hidden_Image_Demo)_(Demo).png" width="100%"></image></a>

Since, I have obtained the files for both [Amazon][amazon-mp3] and [Google Play][gp-mp3], I am providing it here. I can do this as I retain the copyright to my own file I made. There are other things that these stores have modified (some of which I am okay with, some of which I don't agree with), but merging the tracks is a deal breaker to me as that ruins the audio itself and takes away from some of the hard work that any artist would put in to a song designed like this. Those other things which I talked about are modifying the tags of the audio file. You can see the [original tags][original-tags-image], [Amazon's tags][amazon-tags-image], and [Google Play's tags][google-play-tags-image].

### Creation of The Hidden Image

For those interested in how I created the hidden image, I took my SVG for my logo (for clearest quality), turned it into a 48x48 pixel image (because I am not waiting for hours for processing a bigger image), and then ran it through a [perl script][spectrogram-perl] I found off of devrand's website. I included the script on my blog as I had to use the Wayback machine in order to be able to find the script. The site has been offline for a long time now. I can also legally copy it as it is licensed under the [BSD license][bsd-license] and I am crediting the author, Gavin Black, for his wonderful work. You can get the script from the Wayback machine, [here][original-spectrogram-perl] and view the original post, [here][spectrogram-blog-post].

The new audio file that contains the hidden image will look like:
<a target="_blank" href="/postdata/2017-11-20-Music-Artistry/images/Screenshot from 2017-11-16 17-00-41.png"><image src="/postdata/2017-11-20-Music-Artistry/images/Screenshot from 2017-11-16 17-00-41.png" width="100%"></image></a>

You can download a copy of this particular file, [here][48x48-audio], or just listen to it below:
<center>
<audio controls>
  <source src="/postdata/2017-11-20-Music-Artistry/audio/SenorContento-48x48.png.wav" type="audio/wav">
  Your browser does not support the audio element.
</audio>
</center>

### Project Files

Lastly, if you wanted to try out this project for yourself, I am providing the Audacity files for both the [Siren][audacity-siren] clip and the [Hidden Image File Siren][audacity-hidden-image-siren]. These are compressed into zip files. If you cannot unzip them, just visit my site's repository on Github. You will find the link below the post.

### My Files

Now, I am providing these files for free as I just created this file to mess around with some concepts and I want to release this file for free. Obviously, I plan on selling my music if I ever actually make music, especially since music is not something I can just throw together. I just need to figure out how to sell my music without having anyone change the files so I can have the music the way I want it to sound and have other people enjoy it that way too.

Given this, I am giving these files the licenses of [Attribution-ShareAlike 4.0 International (CC BY-SA 4.0)][media-license] for the pictures and audio, or any other media that I can give you rights to and have included on this page (does not include Flickr, that has it's license explicitly stated on Flickr's site) and then I give [GNU GENERAL PUBLIC LICENSE 3][gpl-3-license] for any project files on this page, that I can license. Point being is, I am releasing these works for you to use freely and I expect you to do the same with these works. Obviously I cannot change the license of the perl script, so that does not fall under my license giving, but the audio files, screenshots, and projects that I have uploaded here do get their licenses changed.
