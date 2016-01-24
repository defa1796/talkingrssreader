# Improvement Ideas and Known Problems #

There are lots of things I might like to do to improve this app, but
at this point basic functionality is there, and I need to move on to
other projects.

Accessibility-wise, this app is very useful, but it
does not address the issue of general browsing, and many RSS feeds
carry only summaries.

## Known Issues ##

  * When the app is used soon after waking up the phone, I frequently get SocketException timeouts. It ought to retry and/or check network availability (seems slightly tricky though). Even when successful, first network request takes disproportionately long.
  * I see no convenient way to make the settings (PreferenceActivity) self-voicing.

## Speech-related ideas ##

  * Tag your feeds by language and change TTS language automatically by feed. Or just auto-detect language.
  * Make prosody work and use it to denote titles / styles / other markup.
  * Control to navigate to previous/next paragraph, and to top/bottom.
  * Html parsing ought to be done in background ahead of time, rather than when we're about to display an article.
  * Better yet, remove the html parser and find utterances in javascript.
  * Integration with the AccessibilityService to avoid double speaking of some cues.

## General Functionality Ideas ##

  * Resume speaking after changing speech rate.
  * Remember the last visited feed.
  * Optional auto-forwarding to the next article would be nice, except nearly all articles have "crap" at the end that you don't really want to listen to.
  * Consider having `MEDIA_PREVIOUS` skip back a sentence. Less consistent but more convenient.
  * Remember current position in article on orientation change.
  * Ignore automatic screen orientation change: it can be an issue when jogging apparently.
  * Persistance of articles. And then we can do search.
  * Browse list of article titles.
  * Option to dump an article to sdcard for debugging.

## Google Reader functionality ##

  * Get Google Reader feed by user label. Easy enough, just like FeedsListActivity.
  * Tag articles and feeds: needs UI.
  * Keep read, mark all unread, show unread counts. Control whether to exclude read articles.
  * Sharing.