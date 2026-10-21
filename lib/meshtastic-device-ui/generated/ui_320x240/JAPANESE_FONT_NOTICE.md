# Japanese font

`ui_font_japanese.c` is generated from Noto Sans JP at 14 px and 2 bpp. It contains
ASCII, kana, Japanese punctuation, full-width forms, and the 2,136 characters in the
Joyo Kanji list. Noto Sans JP is distributed under the SIL Open Font License 1.1;
the complete license is in `NotoSansJP-OFL.txt`.

The Joyo Kanji character list used for subsetting is from
[hiroshi-manabe/Joyo-Kanji-List](https://github.com/hiroshi-manabe/Joyo-Kanji-List).
The current input helper converts romaji to hiragana. It does not provide kana-to-kanji
conversion or a Japanese menu translation.
