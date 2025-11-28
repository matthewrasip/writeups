# Hidden in Plainsight
#### debug info: [u:953389 e: p: c:524 i:297123]

## Description
You’re given a seemingly ordinary JPG image. Something is tucked away out of sight inside the file. Your task is to discover the hidden payload and extract the flag.

# Approach
Given the title and how we are provided a JPG image, we can deduce that this problem is about steganography.<br>
We can use `exiftool` to view the metadata of the image: `exiftool img.jpg`.
```
ExifTool Version Number         : 12.40
File Name                       : img.jpg
Directory                       : .
File Size                       : 72 KiB
File Modification Date/Time     : 2025:11:07 19:17:39+00:00
File Access Date/Time           : 2025:11:28 08:27:23+00:00
File Inode Change Date/Time     : 2025:11:28 08:27:23+00:00
File Permissions                : -rw-rw-r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Comment                         : c3RlZ2hpZGU6Y0VGNmVuZHZjbVE9
Image Width                     : 640
Image Height                    : 640
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 640x640
Megapixels                      : 0.410
```
The value associated with comment seems to be encoded using base64. Decoding it returns `steghide:cEF6endvcmQ=`. This gives us a hint of what to do next - suggesting to use `steghide` command line tool. Decoding the second part of the phrase returns `pAzzword`.<br>
Using `steghide extract -sf img.jpg -xf result.txt` requires us to use a passphrase to access the contents - using the previously decoded password, we retrieve the flag: `picoCTF{h1dd3n_1n_1m4g3_92f08d7c}`