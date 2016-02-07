# reddit-imgur-download
This is a python script which uses imguralbum.py from https://github.com/alexgisby/imgur-album-downloader to download all imgur albums from the front page of subreddits

## Usage
Put imgur-album-downloader in your path as imgurdl

    sudo mv imguralbum.py /usr/bin/imgurdl

And run setup.sh

    ./setup.sh
Or to do everything by hand

Make a folder called Imguralbums in ~/Pictures

    mkdir ~/Pictures/Imguralbums

Make a folder called imgur_down in ~/.config

    mkdir ~/.config/imgur_down
    
Then make a file called subreddits.txt in imgur_down and a file call downloaded.txt
    touch downloaded.txt
    touch subreddits.txt
    touch log.txt 

Enter the name of the sub reddits you want to download from in subreddits.txt. You only need the subreddit name not the full url.

The script will download all imguralbums from the front page of those subreddits and save the images to ~/Pictures/Imguralbums/SUBREDDIT/RANDOMSTRING/

It will also download all dot jpg, png and gif files from those subreddits and save them to ~/Pictures/Imguralbums/SUBREDDIT/RANDOMSTRING.PNG/JPG/GIF
    
And then put them in .cbr archives so they can be read with the comic reader of your choice, meaning the end files with look like ~/Pictures/Imguralbums/SUBREDDIT/RANDOMSTRING.cbr

They can be view with any comic reader

## WARNING

The program will compress and rm all folders in the ~/Pictures/Imguralbums/SUBREDDIT dir

## FAQ

How do I run this on windows?

You have to change a few lines.
change
    downloaded = home + '/.config/imgur_down/downloaded.txt'
    SUBREDDITS = home + '/.config/imgur_down/subreddits.txt'

to 

    downloaded = home + 'C:\\downloaded.txt'
    SUBREDDITS = home + 'C:\\subreddits.txt'

remove 
    os.system("mkdir -p " + home + "/Pictures/Imguralbums/" + i)

And make the folders for the subreddits you have in subreddits.txt by hand

Change home = os.getenv("HOME") to home = 'C:'

And change all "/Pictures/Imguralbums/" to "\\Pictures\\Imguralbums\\"

And change a'' '/' to '\\'

WARNING: I have not tested this at all

