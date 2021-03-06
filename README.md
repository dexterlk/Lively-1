# Lively Discord Website

Contact aidswidjaja#2805 on Discord for more information.

# Development Notes (for future developers) - a comprehensive guide to how this website works
#### Current filepath: ~/README.md
<<<<<<< HEAD
#### Current status: `stable|release|final`

[![Netlify Status](https://api.netlify.com/api/v1/badges/5126413d-b774-4507-bf60-c9e6ead602d4/deploy-status)](https://app.netlify.com/sites/livelydiscord/deploys)

DevNotes are not actively maintained - however website receives minor updates from time to time.

Hi! This README is intended for future developers of this static website. It presumes a basic understanding of:

- HTML5, JSON, CSS3, JS and DOM [(Document Object Model)](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)
- Bootstrap 4 (TWBS) and HTML5 Boilerplate (H5BP)
- CDNs for scripts and images
- Static website hosting on GitHub Pages, Netlify and Heroku
- Git on the command line (you may be able to use SVN but this will not be covered in this README)
- Unix terminal usage

If you're a standard end user, this guide isn't for you. Check with the owner of the server for more information.

*This documentation is issued under the same GPL-3.0 license that the website source code is.*

**Produced by aidswidjaja#2805 (Discord) / @adrianpenguin1 (Twitter) / nstyvm@gmail.com (Email).** Discord is usually the fastest way to contact me, but if it's been a couple of years and I go inactive there then try the other methods too.

### Table of Contents

As of 25 Jan 2020, this website's state is `stable|release|final`.

- Background
- Getting started and dependencies
    - Find the most recent version of this website
    - Deploying this site on your local production machine
    - Other things to note
- Filesystem
- Layout
    - Background Image
		- Supported configurations
	- Navbar
		- Social buttons
	- Utilities
		- Fonts
		- `vh, vw, %` and breakpoints
- Mobile responsiveness
- Deployment

***

### Background

This Lively website has been recreated from scratch after an attack on a previous version of the website which lost all source code. There were a number of security vulnerabilities with the old setup, such as the use of the .tk domain operated by the South Pacific island nation of Tokelau, a territory of New Zealand. This setup comes with a few advantages, such as the source code being open source allowing the code to stay safe. It is also initialised through Git which allows for easy code addition, revision, and deletion, especially of past code edits. The current plan as of 21 Jan 2020 is to host it on Heroku or another static site hosting service such as GitHub Pages or Netlify. 

I am personally not responsible for the content on this website, as this is being managed by the Lively Discord server. Please contact them for more information. Should the Lively Discord server be inaccessible, I will be unable to assist you in regards to hosting as I will probably not have access to it – but, you can use the above contact details if all else fails!

This version of the Lively website is designed to be basic but modular. It contains comments and a simple file structure to allow oncoming developers of this site to easily rework the code without completely starting over. That being said, there is not much functionality included on initial release.

This site is designed for Chrome and Firefox primarily, with secondary support on mobile devices (Safari on iOS, Chrome on Android), and limited support for Microsoft Edge (non-Chromium).

### Getting started and dependencies

This site relies on modern web technologies such as HTML5, CSS3 and JavaScript. I encourage you use a compliant and modern browser (such as Firefox Developer Edition). It's originally structured around the HTML5 Boilerplate from the H5BP Organization, but this structure can change and probably will (as of Jan 21) where no significant commits have been made). 

This website (as of Jan 21) uses [HTML5 Boilerplate v7.3.0 (H5BP)](https://github.com/h5bp/html5-boilerplate/releases/tag/v7.3.0) which is directly linked to the [v7.3.0 tag on GitHub.](https://github.com/h5bp/html5-boilerplate/tree/v7.3.0). The current `master` of this project can be [found here](https://github.com/h5bp/html5-boilerplate/tree/master).

This website (as of Jan 21) uses [Bootstrap v4.4.1 (TWBS)](https://github.com/twbs/bootstrap/releases/tag/v4.4.1) which is directly linked to the [v4.4.1 tag on GitHub.](https://github.com/twbs/bootstrap/tree/v4.4.1). The current `master` of this project can be [found here](https://github.com/twbs/bootstrap/tree/master).

Here is the [basic file structure and usage information](https://github.com/h5bp/html5-boilerplate/blob/master/dist/doc/usage.md) for H5BP. It may have been modified significantly since time of writing (Jan 21). 

Here is the [basic file structure and usage information](https://github.com/twbs/bootstrap/blob/master/README.md#whats-included) for TWBS. It may have been modified significantly since time of writing (Jan 21).

For other scripts and dependencies, there will usually be a comment indicating it's usage. Please also see [#1](https://github.com/aidswidjaja/Lively/issues/1) about potential conflicts between H5BP and TWBS.

Once your're familiar with how this website depends on third-party resources, move onto the next section about getting it on your development machine.

#### Find the most recent version of this website

`master` will usually be the most recent version, but it could also be broken, so check releases on GitHub too. Additionally, someone else may have already worked on this website too, so check for forks. 

>Wait! Have you ensured that you're able to clone to a Git repository? You will not be able to push request to [aidswidjaja/Lively](https://github.com/aidswidjaja/Lively) if it is depreceated, so setup a Git repository remotely for you to store your work on.

Once you're confident you have a good codebase and repository to work with, proceed to `clone` the repo to your machine.

```
git clone https://github.com/aidswidjaja/Lively.git
```

where the URL is your remote repo URL.

#### Deploying this site on your local production machine

If this website is static (or you're only testing static features) you can drag and drop the HTML file into your browser. It will be rendered as a local file, and while convenient, eliminates any server-side testing/scripting you may want to do. However, in many cases it's better to use a web server. It's not neccessary to use Apache or Nginx though. Instead, you can use a web server that's already installed on your machine:

If you are using/have installed Node.js/npm - use `http-server`. See [npm](https://www.npmjs.com/package/http-server) or [GitHub](https://github.com/http-party/http-server) for more information.

If you are using/have installed Python - use `SimpleHTTPServer` or `http.server`, depending on your configuration. See [Python Wiki](https://wiki.python.org/moin/WebServers) for more information.

This [MDN web doc](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/set_up_a_local_testing_server) has great information on web servers and how to host this website on your development machine.

#### Other things to note

- Web browser for testing. I recommend: Firefox Developer Edition (Desktop); Chrome/Chromium Dev channel (Desktop); Safari (iOS); Chrome Dev channel (Android)
- Security vulnerabilities. It might be better to process sensitive information offsite.
- Already implemented (but unused features). At the time of writing, I intended to develop this site for another developer to easily take over and continue work on.
- Already implemented analytics. Check through the code and see if there are any variables that need to be changed. You also might need to investigate environment variables that may have been used but not documented.
- `.gitignore` – Are there any files that were excluded from Git?
- `LICENSE` – Are you adhering by the rules of the GPL-3.0 license (or any other additional legal requirements)? 
- At time of writing, the active domain for the site is `https://livelydiscord.netlify.com` - more information in [Deployment](#deployment).

>My local jurisdiction is NSW, Australia, but I'd also suggest looking at US for especially with DMCA, GPL, Git, and hosting services such as Heroku and Netlify if you're concerned, as well as EU GDPR and India, where this Discord server is located.

Once you're happy with your development environment, you can proceed to the next section!

***

### Filesystem

Here is what the filesystem should look like:

```
.
    404.html                # generic H5BP 404 page - if using GitHub Pages you will need to set YAML front matter
    assets                  # contains all base assets - mostly .zip files
    browserconfig.xml       # H5BP-related
    css                     # contains all css resources from Bootstrap (H5BP CSS has been deleted from the css folder, see [Bootstrap Documentation](https://getbootstrap.com/docs/4.4/getting-started/contents/#css-files))
        social              # contains all css resources for Zocial, the CSS social buttons add-on available on [GitHub](https://github.com/smcllns/css-social-buttons) - some files modified
    doc                     # H5BP-related
    favicon.ico             # website favicon
    H5BP-LICENSE.txt        # H5BP-related
    humans.txt              # SEO-related (H5BP)
    icon.png                # H5BP-related
    index.html              # front page
    js                      # contains all js resources from Bootstrap (see [Bootstrap Documentation](https://getbootstrap.com/docs/4.4/getting-started/javascript/))
    LICENSE                 # GPL v3.0             
    README.md               # this file
    res                     # resources the website uses, such as images. Contains darkened backgrounds based on images in base - more info in Background Image
        base         		# contains original, non-darkened assets of background images       
    robots.txt				# SEO-related (H5BP)
    site.webmanifest		# H5BP-related
    tile-wide.png			# H5BP-related
    tile.png				# H5BP-related
    <pages>                 # site pages (.html) are kept in the root directory because of two reasons: a) Netlify does not read the _redirects file for some reason for a cleaner URL; b) portability to different hosting providers
```

***

### Layout

This website uses a traditional splash screen, followed by text/image content on different pages/areas of the site. 

As of 27 Jan 2020 Flexbox usage is not planned for the site, but this may change in the future.

#### Background Image

See [the original documentation from which the source code derives from.](https://paul-lockett.co.uk/randombackground.html)

14 high-resolution background images are stored in the `res` folder. There is also an image credits Markdown document and a `test` folder which was used for initial testing. The source for these images can be found in the `assets` folder which contains the original .zip file.

A function defined in `js/backgr.js` executes the following instruction set :
- Uses the [`Math.random`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random) function to find a integer between 0 and 13 (inclusive).
- This integer, declared as `randimg` is run through a number of `if else` statements. 
- If `randimg == x` where x is the defined integer, then:
    - Wait for the rest of the document to load (see comments in `backgr.js` for further explanation of `onload` and potential better solutions).
    - Use the [`document.getElementById`](https://developer.mozilla.org/en-US/docs/Web/API/Document/getElementById) to locate the `bod` ID which in this case, is assigned the `<body>` tag in `index.html`.
    - Locate the class selector attribute in the `index.css` stylesheet.
    - Proceed to `onload` the classes into the `<body>` tag in `index.html`

`document.getElementById` loads class names `bgx` and `bg`, where `x` is an integer between 1 and 14 inclusive. 
- `bgx` defines `background-image: url(...` and other background-specific attributes.
- `bg` are common attributes that apply to all backgrounds.

**The `res` folder is the directory which `backgr()` extracts images from, to display on the website as a background. These images are darkened versions of the original images located in the `base` subdirectory. They contain a `rgba(52, 58, 64, 0.7)` layer over them (using Krita).

The problem with `bg` is that it uses the following CSS attributes:

```CSS
.bg {
    background-position: center center;
	background-repeat: no-repeat;
    background-attachment: fixed;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
    background-color: #343538;
}
```

There are a number of issues with the above setup on it's own:
- `background-attachment: fixed` is not supported on Android - see [AOSP Issue 36908439 on Google Issue Tracker](https://issuetracker.google.com/issues/36908439)
- `background-attachment: fixed` when used in conjunction with `background-size: cover` is not supported on Safari - see [Can I use `background-attachment`?](https://caniuse.com/#search=background-attachment)
- `background-attachment: fixed` does not render properly on Chromium for Android - see [Chromium Issue 344338: Bad rendering of fixed background on Android, even with --disable-accelerated-fixed-root-background](https://bugs.chromium.org/p/chromium/issues/detail?id=344338)

That's why we added extra attributes to `html` and `body`, as per the solution in the [CSS Tricks forum archives](https://css-tricks.com/forums/topic/full-page-backgrounds-on-ios-background-size-cover/page/2/#post-134002):
```CSS
html, body {
    margin: 0;
    padding: 0;
    height: 100%; /* Used to ensure that the background fills the entire height of the parent element - vh is not used due to compatibility issues on WebKit */
}

html {
    overflow: hidden;
}

body {
    overflow: auto; /* Changed from scroll to auto to remove white bar at the bottom of the webpage */
    -webkit-overflow-scrolling: touch;
}
```

For some reason, this solution seems to work – I'm not sure why, but it was last tested on 27 January for the following configurations.

##### Supported configurations

**DESKTOP:**
- Chrome Version 79.0.3945.130 (Official Build) (64-bit)
- Firefox Developer Edition 73.0b8 (64-bit)
- Opera 63.0.3368.94
- Microsoft Edge 80.0.361.54 (Official build) (64-bit)

**DESKTOP CONFIG:**
```
ProductName:	Mac OS X
ProductVersion:	10.14.6
BuildVersion:	18G103
```

in addition to `Windows 10 Pro 1909 64-bit`.

***

**ANDROID:**
- Chrome for Android 79.0.3945.136
- Firefox Nightly for Android 68.5a1 (2020-01-20)
- Firefox Preview Nightly 200126 6:00 (Build #20260605) 29.0.0, c3ba2ed42, GV: 74.0a1-20200123095433, Sunday 1/26 @ 6:05 AM

**ANDROID CONFIG:**
```
Android 9
SM-A105G 
Build/PPR1.180610.011
(64-bit CPU, 32-bit arch) - yes, that means no Pokemon Masters for me I get it okay???
```

***

**iOS:**
- Safari on iOS 12, iPhone 6

***

Although the following have not been tested, I am expecting compatibility with:

- Chrome for iOS

I cannot guarantee compatibility with:

- Internet Explorer <9
- Microsoft non-Chromium based Edge (Trident)

***

#### Navbar

The Navbar is a default Bootstrap Navbar that has the following properties:

- Copyright © message: `© Lively 2020` is a disabled `<p>`
- It is mobile responsive, with changes occuring at presumably the `lg` breakpoint
- 100% transparent
- Contains the Lively logo
- Contains social buttons from [smcllns/css-social-buttons](https://github.com/smcllns/css-social-buttons)

##### Social buttons 

The Lively website contains social buttons in the Navbar from a CSS/HTML-only bundle (that has been modified to reflect modern web design). Notably, gradients are commented out in the core files.

The five buttons and their associated class names are listed, in order (according to the official information on the Lively Discord server information channel):

- `twitter`
- `instagram`
- `facebook`
- `stackoverflow` but this represents the Medium blog for which there is no button for
- `discordapp`

These buttons also work lg> breakpoint, however, they appear stacked in the mobile Menu dropdown on the Navbar, which is a real waste of screen real estate!

To respect differences between the desktop and mobile versions of the Menu, separate code (placed inside and outside the `.navbar-nav` div respectively, and using `d-lg-none` and `d-lg-inline` respectively) is used for desktop and mobile viewports.

Usage:

```HTML
<a href="https://discord.gg/hv7u9bT" class="zocial discordapp icon d-lg-none"></a>				# d-lg-none 	| "desktop-sized window"
<a href="https://discord.gg/hv7u9bT" class="zocial discordapp icon d-none d-lg-inline"></a>		# d-lg-inline 	| "mobile-sized window"
```

***

#### Utilities

##### Fonts



