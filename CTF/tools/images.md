# Images in CTFs

	file image.img
Running the file command reveals the following information

	exiftool image.img
Exiftool allows you to read and write meta information in files. Flags may be hidden in the meta information and can easily be read by running exiftool.
sudo apt install libimage-exiftool-perl -y

	strings image.img
The strings command will print out strings that are at least 4 characters long from a file.

	xxd image.img
xxd allows you to take a file and dump it in a hexadecimal (hex) format.
	
	binwalk image.img
Binwalk is a tool that allows you to search binary images for embedded files and executable code
sudo apt install binwalk -y

There are many other tools available that will help you with steganography challenges. Below are a few more that you can research to help expand your knowledge.

    stegsolve
    pngcheck
    stegdetect

*Reference*
https://infosecwriteups.com/beginners-ctf-guide-finding-hidden-data-in-images-e3be9e34ae0d
