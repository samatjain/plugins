Records a text-to-speech synthesized version of each post in every
language. Can be embedded using the HTML5 audio element with three
fallback formats, or subscribed to as a netcast/podcast.

Supports Opus, Vorbis, and optionally MP3s. Offering full web
browser-support and support with every netcast aggregator. One feed
is generated per format per language. Uses the FEED_LENGTH option to
determine how many files to include in the netcast feeds, but audio
files are generated for all posts.

Speech synthesis powered by [Espeak](http://espeak.sf.net).
Pronunciation is understandable in most languages. As a free and
open-source program, you can add a [new or improve](http://espeak.sourceforge.net/add_language.html)
a language fairly easily.

## Installation

System level dependencies:

* espeak (with voice data for desired languages)
* sox
* flac
* opus-tools
* vorbis-tools

Optionally:

* lame (see MP3 below)

## HTML5 audio element

The below code example can optionally be used inside a Mako
template to add an audio player on your posts.

    <audio controls="controls">
      <source src="${post.permalink(lang=lang, extension='.opus')}" type="audio/opus">
      <source src="${post.permalink(lang=lang, extension='.oga')}" type="audio/ogg">
      <source src="${post.permalink(lang=lang, extension='.mp3')}" type="audio/mpeg">
      <p>Your browser does not support audio. Download the
        <a href="/audio/posts/${post.meta[lang]['slug']}.oga">audio file</a> locally instead.</p>
    </audio>

## MP3

MP3 files are not generated by default. MP3 is the audio file format
with the widest support among web browsers and netcast aggregators.

Optional MP3 support in *Speech Synthesized Netcast* for Nikola is
powered by the [LAME](http://lame.sf.net) encoder.

The below IS NOT legal advice, just a strong warning to seek it.

Virtually any distribution of MP3 files *may* **require a paid
license** in your jurisdiction. These fees are for patents related
to the MP3 technologies. Please seek legal counsel before beginning
to distribute MP3 files. The “MP3 patents” expired in most countries
in December 2012. Two notable exceptions is the United States and
Japan, where they should expire by May 2017 and November 2021.

It is recommended to use the free Opus and Vorbis formats instead
of MP3. At least, offer one of the free alternatives so that MP3
eventually can be put to rest. Learn more at [PlayOgg](http://playogg.org).