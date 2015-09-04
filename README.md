﷽

# Quran Memorizer Thingy
(diz app haz no proper name yet)

## Background

I was experimenting ways to better memorize the surahs from Quran. I started playing with an idea and @tengkuhafidz helped built a prototype from my primitive idea.

As I developed the idea further, I ended up with deciding that one of the best way to memorize is to listen to a recitation. So I decided to build this prototype to test my hypothesis.

There are already apps out there which provides Quranic verses with recitations. However, what I was looking for is an app which I can pinpoint at the exact word and it'll start reciting from there. Why? Because often when we are trying to memorize, we might get stuck halfway through the verse, and if it's a long verse, having to listen to the reciter from the start takes quite some time.

## About

This repo consist of 2(+1) parts.

1. Word-by-word recitation interface
2. Word-by-word assigner interface
3. Old prototype when I was experimenting with memorizing by rearranging verses/words.

### Word-by-word Recitation Interface

Run `jqw_sort.html` in your browser. Click on any word to get the app to start reciting from that position.

Currently, only surah Al-Mulk is fully assigned/implemented. This is the surah that is automatically loaded. An-Nisa is in progress.

### Word-by-word Assigner Interface

Run `jqw_sort.html?playMode=false` in your browser. This mode is to be used to build the relation between the words and the exact timing in the audio file. In this mode, recitation is slowed down to 0.8x the original speed.

Keys:
- `Enter`: Pause/Play
- `Spacebar`: Associate Playback Time to Word
- `Backspace`: Remove Timing-Word Association
- `Left/Right` Arrow Keys: Seek Forward/Backward
- `\`: Save to LocalStorage

As the surah is being recited, press `Spacebar` before the word is being recited to mark the starting position of that word. If you make a mistake, press `Backspace`. Press `\` key to save the current progress to your LocalStorage.

On next load of this page, the app will load from your localStorage. Right now, there is no way to export this data except through writing some JS codes.

#### Important Files

- \*.mp3: The recitation file. Using Mishary
- quran.json: The whole quran in JSON format, word-by-word
- translations.json: The translations, word-by-word (extracted from http://corpus.quran.com/wordbyword.jsp by me)
- timemarks.json: Hold the relationship between recitation audio and which word in the Quran

The JSON saved into the localStorage is supposed to be placed into timemarks.json when finalized.

### Old prototype

Run `jq_sort.html`. Just a drag-and-drop prototype of first 10 verses of surah Al-Mulk. The verses order are jumbled up and you're supposed to order it to the correct order. Nothing fancy.

## WARNING

Code is largely undocumented, but should be very understandable. Proceed at your own risk.

## License

Released under GPLv2.
