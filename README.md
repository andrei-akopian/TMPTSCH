# [TMPTSCH](https://andrei-akopian.github.io/TMPTSCH/index.html)
Stands for **Takahashi Method Presentation Tool Sent Clone HTML**

As the name suggests this is a presentation making tool based on the [Takahashi method](https://en.wikipedia.org/wiki/Takahashi_method) and inspired by the [sent](https://tools.suckless.org/sent/) (from [suckless.org](https://suckless.org/)), [Weenote](https://github.com/jed/weenote), and [Big](https://github.com/tmcw/big), while also maintaining some compatibility with them. 

But contradictory to the principles of the method this Clone is bloated with functionality while remaning a single html file so you can easily save and use it offline.

My Blog post: [About Takahashi Method](https://andrei-akopian.bearblog.dev/about-takahashi-method/)

### Purpose

The purpose of this application is to display presentations generated from TXT files (other file formats might happen to work but are not supported). The editing features are not intended be used for making presentations, only quick edits for typos.

# [DEMO](https://andrei-akopian.github.io/TMPTSCH/demo)

# [Open WebApp](https://andrei-akopian.github.io/TMPTSCH/index.html)

## Install/Download

### Web version
If you already have a (text-only) presentation file for the original `sent`, you can go streight to [the site](https://andrei-akopian.github.io/TMPTSCH/) and click `Choose File` in the top left corner.

Why text only (no images)?

Obviously the website can't read images that are localy on your computer. However, using `@https://upload.wikimedia.org/wikipedia/en/a/a9/Example.jpg` (a link to an image) also works. Note that this feature isn't backward compatible with `sent`.

### Download

If you want it all to be local with no contact to the internet, you can just hit `Ctrl + S` (or  `Cmd + S` on Mac) and save the website as html. 

Because of the way I made it, it will remain as a single file and the slides you already created will be saved as well (except images, those will be downloaded into a spearate folder and all the link will be a mess).

Warning: when you hit `Ctrl + S` you browser will offer you 3 options:
- `Webpage, HTML Only`: Won't save any of your progress
- `Webpage, Single File`: Will save everything into a `.mht` (Microsoft) format that in traditional Microsoft fashion is impossible to open.
- **`Webpage, Complete`:** is the one you want to choose, but it is also the one that will download your images (and `qrcode.js`) into a folder and they will break.

## Usage

Standard `sent` syntax, if you know it, you are good to go. (check image syntax tho!)

For example see `demo.md`.

If you don't, come back another day when I have better instructions ready.

Have and save every version of your presentation. Because the
- [ ] slide insertion and
- [ ] slide deletion
are not yet implemented, you have no way of undoing anything you did (other than resetting to a backup).

### Hotkeys

`e` toggles the slide editor.

`h` toggles the header and the editor.

`r` regenerates the slides (use after resizing the window or changing formatting options)

`f` toggles fullscreen

Arrow keys can be used to navigate slides.

### Images

You can save this tool/presentation as a `.html` file by hitting Ctrl + S as I described in the [Download](#download) section, you will be able to get image files using usual `@image.png`.

If you are using the [online version](https://andrei-akopian.github.io/TMPTSCH/), you won't be able to use local images, but you can instead link images through their url (`@https://example.com/image.png`). 

### Presenter's Notes
`//` will treat the whole line as presenter's notes. 

The notes will be printed to the dev console of your browser (the printing behavior will be a bit wonky, but it does give you the slide number). (btw, it is possible to pop out the developer console into a separate window). 

You should only have 1 comment line per slide, but if you have mutiple it will still work.

If the Parse Comments **checkbox is checked** upon the addition or new slide content's are entered, the presenter's notes will be saved using an invisible `<notes>` tag and will appear in the console when going to a news slide.

### QR Codes and Hyperlinks

If you enter links in the markdown format `[Example](https://example.com/)` the link will be converted into a `<a>` html tag. By default the QR Code feature will be disabled, and the links will open in a new tab.

QR Codes features is implemented using [qrcode.js](https://davidshimjs.github.io/qrcodejs/). You can choose where you wish to load the library from using the dropdown (Local, or CDN). If you are using the github pages site, selecting the local option will work as a `qrcode.js` script is in this repository, but if you have downloaded this app you might want to use the CDN (by Cloudflare) option, and if it gets cached in your browser it should work even offline.

- [ ] I will figure out how CDNs work and make the loading simpler, mb allow saving QR codes as pngs.

Open a QR code by clicking on the hyperlink text, and close it by clicking on the QR code itself.

## Roadmap/Features

### Features

Features:
- dark/light modes

Custom features:
- all links open/autogenerate QR codes when in slide mode
- single html file
- [ ] minimize JS and html for space?
- included text editor
  - add new slides for text editor
- easy saving
  - saving text file
  - [ ] nice pdf printing formatting
- loading multiple files
- [ ] sideloading images
  - [ ] base encode images for saving
- [ ] special markdown formatting
- [ ] make an additional tool that downloads all url linked images

### Comparison

Feature coverage and compatibility with other (similar) tools.

*Feature modifications are in italic*

[sent](https://tools.suckless.org/sent/) (from [suckless.org](https://suckless.org/)) *~~(Non-)~~* features:
- A presentation is just a ~~simple text~~ *complicated html* file.
- Each paragraph represents one slide.
- Content is automatically scaled to fit the screen.
- [ ] UTF-8 is supported.
- Images can be displayed (no text on the same slide).
- Just around ~~1000 lines of C~~ *a tone of javascript*
- [ ] ~~No~~ different font styles (bold, italic, underline) *and fonts*
- [ ] No fancy layout options (different font sizes, different colors, …)
- [ ] No animations
- [ ] No support for automatic layouting paragraphs
- No export function. If you really need one, just use a shell script with xdotool and your favorite screenshot application.
  - Export back to a .txt file.
  - [ ] pdf export
- [ ] Slides with exuberant amount of lines or characters produce rendering glitches intentionally to prevent you from holding bad presentations.

[Big](https://github.com/tmcw/big) features:
- print all presentation comments into the console
- [ ] controls
- [ ] jump menu

[Weenote](https://github.com/jed/weenote)
- [ ] campatibility

[Slide](https://github.com/trikita/slide)
- [ ] Steal syntax for markdown formatting

## Credit

A lot of the code was written with Weenote and Big as references.

[qrcode.js](https://davidshimjs.github.io/qrcodejs/) for QR Code generation. (and Cloudflare CDN for loading the script form the web)

Used [Lorem Picusm](https://picsum.photos/) and [Placehold](https://placehold.co/) for demo placeholder images.

### Contribute? / Docs

I don't know why you would want to do something here, but if you do be ready for an absolute mess of a CSS and a bunch of spaggetti code. In order to handle QR Codes, comments, and the editting features all while making sure you can save and open the file without anything breaking, I made the code a complete mess.

And yes there are quite a few "you have to do this, because if you don't an edgecase breaks" sort of things.

Because this is my first "major" app, there is no consistency in the code whatsoever, and although I did try to follow "best practices," manage your expectations.

Everything Should be Inline to make the thing remain a single HTML file.

Colors:
Blue: `#0A73A7` and `#0A42C5`
Orange: `#E2A619` and `#E29002` and `#C37515`

Demo Design:
- On a fresh browser profile (no extensions) import from demo.md
- turn hide the header menu
- after saving, change all urls and image links to what they are supposed to be
- turn off image source detection and click event listener
- check the differences between old and new demo files

Favicon:
- to keep it all a single file, a separate version of the favicon is inline
  - Encode using this: https://yoksel.github.io/url-encoder/