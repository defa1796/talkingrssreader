# About the Code #

## What's interesting in this code ##

The synchronization of speech with page scrolling is achieved through
an interesting technique involving bidirectional communication between
the Android app and a piece of javascript running in the WebView.

There may be interest in the code that walks the DOM tree, splitting
the text into utterances corresponding to sentences, and adding
indications for things like links, list bullets, quotations, flow
breaks... In retrospect however, this should have been done in
javascript rather than with an HTML parser.

The TalkingWebView functionality can conceivably be transplanted and
reused in a different app. This is nowhere near a generic web
accessibility solution, but it can speak simple HTML text. I did
manage to insert TalkingWebView and its many dependencies into an
E-mail app and have it read the body of an E-mail message.

The code also shows how to make some UI components self-voicing. There
is a reusable focus announcer and text watcher that are good for
buttons and EditTexts. There is a spoken error dialog and spoken
toasts. There is a talking ListView, adapted by using an
OnItemSelectedListener to track focus. Speaking out the options menu
required that I reimplement the menu with a ListView, because the
built-in menu lacks a callback on item focus change.

The following is no longer true: as of version 1.5.0 (July 2010) the
Android built-in text-to-speech service is now used.

This app relies on a modified version of the TTS for Android package
from
[the Eyes-free project](http://eyes-free.googlecode.com),
which is based on
[the eSpeak speech synthesizer](http://espeak.sourceforge.net/).
The modified TTS is bundled inside the Talking RSS Reader application
package. The modifications I made are for much increased
responsiveness, using the Android AudioTrack API, reworked threading,
and to make it possible to reliably track speech progress with a fancy
speech completion callback. See
[this README](http://talkingrssreader.googlecode.com/svn/snappytts/snappytts/README)
for more details.

Development of the
[Eyes-free project's TTS](http://eyes-free.googlecode.com)
has stopped, as far as I know, since the announcement
that SVOX is coming to Android's _donut_ release. Therefore the
modifications made for this app will not be folded back into the
Eyes-free project TTS. The modified TTS bundled with this app was
tweaked so as not to interfere with another installed system-wide TTS
service. If anyone would prefer to use this espeak-based TTS, whether
bundled with an app or as a system-wide service, then the code in this
repository should be of interest.

## HTML parser dependency ##

This application uses the HTMLParser library from
http://htmlparser.sourceforge.net, version 1.6 (Release Build Jun 10, 2006,
htmlparser1\_6\_20060610.zip).

## Some credits ##

Thanks to GP from
[LivelyBlue.com](http://www.livelyblue.com)
for the beautiful icon.

The sound clip in res/raw/woowoo.ogg was extracted from a sound file
from http://www.pdsounds.org/.

## Some Google Reader API references ##

http://code.google.com/p/pyrfeed/wiki/GoogleReaderAPI
http://www.niallkennedy.com/blog/2005/12/google-reader-api.html