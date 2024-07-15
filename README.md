# Invoke-Binwalk

## what?

binwalk for powershell/.net

## ...why?

a certain fishy security product forced the necessity of scraping gzip files from a very large raw disk image, and due to restrictions not worth excepting python was unavailable, so i developed a powershell script to do what binwalk does

## how does it work?

basically it breaks the disk image into chunks, and then takes three passes at each chunk. pass one identifies the index (byte address) of the headers of each file, pass two starts at each header index and seeks out footer/eof (end of file) and associates them with the indices, and pass three extracts the bytes to files.

currently, the only built-in file type is the specific style of gzip the aforementioned product used for compressing the files they used, but the desired endstate is to operate like binwalk, where you can pull a signature file and use that as your header and footer/eof

### use

<todo>
