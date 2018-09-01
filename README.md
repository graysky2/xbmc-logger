## Description
A simple perl script that will keep a log of everything you watch on kodi without showing repeated entries.

## Dependencies
* Perl

## Installation and Setup
Currently, two versions are supplied, one supporting kodi version 17.x and one supporting kodi version 18.x.

Copy the correct version of script to a public directory such as /usr/local/bin and make it is executable.
```
% cp /path/to/kodi17-logger.pl /usr/local/bin/kodi17-logger
% chmod 755 /usr/local/bin/kodi17-logger
```

The script expects to have write access to `/var/log/kodi-watched.log` so you will need to manually create this file and change the ownership of it to the user who shall run the script:

```
# touch /var/log/kodi-watched.log
# chown myuser:mygroup /var/log/kodi-watched.log
```

## Usage
To use kodi-logger, simply call the script at some regular interval (once every 5 min for example) which is easily accomplished in your crontab:

```
crontab -l
*/5 * * * *	/usr/local/bin/kodi17-logger
```

The extracted output is saved to the directory you specify in the script itself and simply shows the date/time and file name that was viewed.

## Example log
```
Thu Jul 18 10:50:01 2013 /media/DVD_Rips/Sopranos/Season_3/3x01-Mr._Ruggerios_Neighborhood.mkv
Thu Jul 18 12:50:01 2013 /media/DVD_Rips/Sopranos/Season_3/3x02-Proshai_Livushka.mkv
Thu Jul 18 22:50:01 2013 /media/DVD_Rips/Sopranos/Season_3/3x03-Fortunate_Son.mkv
Fri Jul 19 20:20:01 2013 /media/DVD_Rips/Movies/There_Will_Be_Blood.mkv
Sat Jul 20 20:30:02 2013 /media/DVD_Rips/Movies/The_Girl_With_the_Dragon_Tattoo_2011.mkv
```
