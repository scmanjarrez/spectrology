# spectrology
Images to audio files with corresponding spectrograms encoder.
The encryption of the audio is performed using AES-CFB using
MD5(pass1) as Key and MD5(pass2) as IV.

## Usage

```
usage: spectrology.py [-h] [-r] [-o OUTPUT] [-b BOTTOM] [-t TOP] [-p PIXELS]
                      [-s SAMPLING] [-e | -d] [-p1 PASS1] [-p2 PASS2]
                      INPUT

positional arguments:
  INPUT                 Name of the image to be convected.
	                    Name of the audio to be decrypted.

optional arguments:
  -h, --help            show this help message and exit
  -r, --rotate          Rotate image 90 degrees.
  -o OUTPUT, --output OUTPUT
                        Name of the output wav file. Default value: out.wav).
  -b BOTTOM, --bottom BOTTOM
                        Bottom frequency range. Default value: 200.
  -t TOP, --top TOP     Top frequency range. Default value: 20000.
  -p PIXELS, --pixels PIXELS
                        Pixels per second. Default value: 30.
  -s SAMPLING, --sampling SAMPLING
                        Sampling rate. Default value: 44100.
  -p1 PASS1, --pass1    Password Key
  -p2 PASS2, --pass2    Password IV

mutual exclusive arguments:
  -e, --encrypt         Encrypt audio file.
  -d, --decrypt         Decrypt audio file.
```

```
python spectrology.py test.bmp -b 13000 -t 19000
python spectrology.py test.bmp -e -p1 hola -p2 mundo
python spectrology.py enc.wav -d -p1 hola -p2 mundo
```
![spectrogram](https://solusipse.net/blog/img/posts/audio-samples/7.png)

For more informations on this techique, see this article: https://solusipse.net/blog/post/basic-methods-of-audio-steganography-spectrograms/.

## License
See `LICENSE`.
