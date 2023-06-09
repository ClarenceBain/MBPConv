# MBPConv

MBPConv converts MovieBoxPro downloaded media into a clean readable format made ready for use with a program like Plex or Jellyfin. 

This project has always been made for my personal use, which will explain the lack of CLI support or a general "program" feel, but it doesn't hurt to make it available for whoever may come across this.

This project is also highly based off of having access to an iPhone thats been jailbroken/TrollStore'd because it requires the MovieBoxPro third party application and Filza.
You can determine if your device is compatible by checking out the [jailbreak wiki.](https://www.reddit.com/r/jailbreak/wiki/index/)

Its entirely possible this will work with Android devices, but I don't have access to one and don't plan on getting one so you'll have to mess around yourself.

MBPConv works by reading through the ***Download.db*** file location within the application documents directory of MovieBoxPro, and gathering the information required to format media files into a readable format.
It also supports subtitles, which require the ***Subtitle_Cache*** directory to be copied over along with the ***Download.db***.

Both ***Download.db*** and ***Subtitle_Cache*** must be in the same folder as all the media you have downloaded, downloaded media can be found within the ***MBDownload*** directory within the application documents directory.

Using this script, it would turn the file downloaded from MovieBoxPro, "Man of Steel_1604_1080p.mp4" into "Man of Steel (2013).mp4" and would fetch the priortized subtitles for it.

TV shows are whole separate beast in terms of functionality, the download layout being: 
- Original: Breaking Bad_1234 --> season_1 -- > 1.mp4, 2.mp4, 3.mp4, etc..
- Converted: Breaking Bad (2008) --> Season 01 --> Pilot S01E01.mp4, Cat's in the Bag... S01E02.mp4, etc..

## Errors, bugs, and general documentation

With my testing i've come across a few bugs that aren't that much of a pain, but could be a little annoying at times, i'll list them below.

1. Bad/wrong subtitles
   - MovieBoxPro prioritizes subtitles usually on user feedback, some media especially older fail to have user feedback and will prioritize random subtitles or terrible subtitles. There is nothing in code I can do to fix this, but you can set correct priority within the MovieBoxPro application once the file is downloaded, but you'd need hindsight for this.
   - You can fix this post conversion by going to the movie folder within ***Subtitles_Cache\Subtitles_My_Cache\*** and just grabbing the correct/working .srt file.
2. m[18] is returning empty and subtitles aren't being found/prioritized/copied
   - This is normally user error, within MovieBoxPro settings the user must enable "Select Subtitle Automatically" under Playback.

During my testing (still on-going), in total I converted about 200 movies and 3 of them had bad subtitles/not working subtitles, so 1.5% were bad.

## License

This project is licensed under the [MIT License](LICENSE.md)

As a developer you get control over:
- Commercial use
- Modification
- Distribution
- Private use 

Find out more information about the [MIT License](LICENSE.md)

## Acknowledgments

  - The developers of [MovieBoxPro](https://www.movieboxpro.app/)
  - The developers of [Filza](https://www.tigisoftware.com/default/?page_id=78)
