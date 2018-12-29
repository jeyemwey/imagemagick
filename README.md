# madhead/imagemagick

Simple [Docker](https://docker.com) image for hustle-free image conversions with [ImageMagick](https://imagemagick.org).

## Usage

First, pull the image:

    docker pull madhead/imagemagick:latest

Then, do the simple conversions like:

    docker run --rm -it -v $(pwd):/src -v $(pwd):/out --user=$(id -u):$(id -g) madhead/imagemagick convert /src/image.svg /out/image.png

or more sophisticated ones:

    docker run --rm -it -v $(pwd):/src -v $(pwd):/out --user=$(id -u):$(id -g) madhead/imagemagick convert -density 300 /src/document.pdf -background white -alpha remove -quality 90 /out/document.png

Read about the available flags, options and switches in the official [ImageMagick documentation](https://imagemagick.org/script/convert.php).
[Ubuntu's manpage](http://manpages.ubuntu.com/manpages/precise/en/man1/convert.1.html) is great as well.
Docker options are described in details [on their site](https://docs.docker.com/engine/reference/run).

## Contributing

Do not hesitate to [open an issue](https://github.com/madhead/imagemagick/issues/new) in case you notice any bugs or missing conversion tools or features.
Read the [contributing guide](CONTRIBUTING.md) if you know how to hack and make the image better.

## Aliases
 
If you are using Bash, you can link to this image from your `~/.bashrc`. Just add the following aliases to the end of the file:
 
```bash
alias madheadImagemagick="docker run --rm -it -w=/src -v $(pwd):/src --user=$(id -u):$(id -g) madhead/imagemagick"
alias magick="madheadImagemagick magick"
alias magick-script="madheadImagemagick magick-script"
alias animate="madheadImagemagick animate"
alias compare="madheadImagemagick compare"
alias composite="madheadImagemagick composite"
alias conjure="madheadImagemagick conjure"
alias convert="madheadImagemagick convert"
alias display="madheadImagemagick display"
alias identify="madheadImagemagick identify"
alias import="madheadImagemagick import"
alias mogrify="madheadImagemagick mogrify"
alias montage="madheadImagemagick montage"
alias stream="madheadImagemagick stream"
```

After running `source ~/.bashrc`, you can just use the [ImageMagick commands](https://imagemagick.org/script/command-line-tools.php) like this: `convert rose.jpg -resize 50% rose-smaller.jpg`.
