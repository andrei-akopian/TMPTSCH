# TMPTSCH
Stands for **Takahashi Method Presentation Tool Sent Clone HTML**

As the name suggests this is a presentation making tool based on the [Takahashi method](https://en.wikipedia.org/wiki/Takahashi_method) and inspired by the [sent](https://tools.suckless.org/sent/) (from [suckless.org](https://suckless.org/)), [Weenote](https://github.com/jed/weenote), and [Big](https://github.com/tmcw/big), while also maintaining some compatibility with them. 

But contradictory to the principles of the method this Clone is bloated with functionality while remaning a single html file so you can easily save and use it offline.

# [Try](https://andrei-akopian.github.io/TakahashiSentHtml/)

## Install/Download

### Web version
If you already have a (text-only) presentation file for the original `sent`, you can go streight to [the site](https://andrei-akopian.github.io/TakahashiSentHtml/) and clicl `Choose File` in the top left corner.

Why text only (no images)?

Obviously the website can't read images that are localy on your computer. However, using `@https://upload.wikimedia.org/wikipedia/en/a/a9/Example.jpg` (a link to an image) also works. Note that this feature isn't backward compatible with `sent`.

### Download

If you want it all to be local with no contact to the internet, you can just hit Ctrl + S and save the website as html. Because of the way I made it, it will remain as a single file (and the slides you already created will be saved as well).

- [ ] Features described above are not yet polished.

## Usage

Standard `sent` syntax, if you know it, you are good to go. (check image syntax tho!)

If you don't, come back another day when I have better instructions ready.

### Hotkeys

`e` toggles the slide editor.

`<-` and `->` arrows can be used to navigate slides.

### Images

If your have saved the this tool as a `.html` file by hitting Ctrl + S as I described in the [Download](#download) section, you will be able to get image files using usual `@image.png`.

If you are using the [online version](https://andrei-akopian.github.io/TakahashiSentHtml/), you won't be able to use local images, but you can instead link images through their url (`@https://example.com/image.png`). 

## Roadmap/Features

### Features

Features:
- [x] dark/light modes

Custom features:
- [ ] all links open/autogenerate QR codes when in slide mode
- [X] single html
- [ ] minimize JS and html for space?
- [X] included text editor
  -  [x] add new slides for text editor
- [x] easy saving
- [x] loading multiple files
- [ ] sideloading images
  - [ ] base encode images for saving
- [ ] special markdown formatting
- [ ] nice pdf printing formatting

### Comparison

Feature coverage and compatibility with other (similar) tools.

*Feature modifications are in italic*

[sent](https://tools.suckless.org/sent/) (from [suckless.org](https://suckless.org/)) *~~(Non-)~~* features:
- [x] A presentation is just a ~~simple text~~ *complicated html* file.
- [x] Each paragraph represents one slide.
- [x] Content is automatically scaled to fit the screen.
- [ ] UTF-8 is supported.
- [x] Images can be displayed (no text on the same slide).
- [ ] Just around ~~1000 lines of C~~ *a tone of javascript*
- [ ] ~~No~~ different font styles (bold, italic, underline) *and fonts*
- [ ] No fancy layout options (different font sizes, different colors, …)
- [ ] No animations
- [ ] No support for automatic layouting paragraphs
- [ ] No export function. If you really need one, just use a shell script with xdotool and your favorite screenshot application.
- [ ] Slides with exuberant amount of lines or characters produce rendering glitches intentionally to prevent you from holding bad presentations.

- [ ] make an additional tool that downloads all url linked images

[Big](https://github.com/tmcw/big) features:
- [ ] print all presentation comments into the console
- [ ] controls
- [ ] jump menu

[Weenote](https://github.com/jed/weenote)
- [ ] campatibility

## Credit

A lot of the code was written with Weenote and Big as references.