# Learning accessibility (a11y)

Just one of the things I'm learning. <https://github.com/hchiam/learning>

This repo's link is easier to remember/type. It serves as a redirect to find this repo faster:

<https://github.com/hchiam/web-accessibility-course-notes>

Start with the above link. Extra notes may be added to this repo too.

Deque prep course for IAAP WAS: <https://dequeuniversity.com/curriculum/packages/iaap-was>

## Key things I personally focus on most

1. Use [WAVE](https://chrome.google.com/webstore/detail/wave-evaluation-tool/jbbplnpkjmmeebjpijfedlgcdilocofh) or some other automated a11y checker, like [axe DevTools for Firefox](https://addons.mozilla.org/en-US/firefox/addon/axe-devtools) or lighthouse or [axe DevTools for Chrome](https://chrome.google.com/webstore/detail/axe-devtools-web-accessib/lhdoppojpmngadmnindnejefpokejbdd).
2. Use a [screen reader](https://www.youtube.com/watch?v=5R-6WvAihms&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g&index=7).
3. Tab. Shift+Tab. Enter. (And screen reader + arrow keys.)

## Some a11y-related CodePens

- [accessible to-do list](https://codepen.io/hchiam/pen/ExWLExQ)
- [Accessible Abbreviation Tooltips](https://codepen.io/hchiam/pen/MWpXXLK)
- [draggable and editable element](https://codepen.io/hchiam/pen/pobxgBo) - try using a mouse, touchpad, or keyboard to move and edit the element!
- [`aria-labelledby` "loop" (not really)](https://codepen.io/hchiam/pen/VwpBPvx)
- [definition/description list](https://codepen.io/hchiam/pen/zYZLNzd)
- [iframe for scoping JS and CSS?](https://codepen.io/hchiam/pen/ExWpZbb)
- Accessible link that opens in new window: (note that using an HTML-only solution instead of CSS `::before`/`::after` `content` basically guarantees compatibility across browser/screen reader combos)
  - [version 1 of Accessible link that opens in new window](https://codepen.io/hchiam/pen/dyvedQj)
  - [version 2 of Accessible link that opens in new window](https://codepen.io/hchiam/pen/NWpBdmr)
  - [version 3 of Accessible link that opens in new window](https://codepen.io/hchiam/pen/ExWpXEo)
- [visually hidden spans (`<del>` and `<ins>` and `<mark>` example)](https://codepen.io/hchiam/pen/YzZjQwv) for text that is visually crossed out, inserted, or highlighted
- [Accessible SVG](https://codepen.io/hchiam/pen/ZEejXoE)
- [Icon Fonts (text acting as an image)](https://codepen.io/hchiam/pen/jOBpaEO)
- [Stylesheet HTML media attribute alternative to CSS media queries](https://codepen.io/hchiam/pen/poeZmVB)
- [more visually accessible/responsive table](https://codepen.io/hchiam/pen/MWpBMpy)
- [accessible font size tips](https://codepen.io/hchiam/pen/JjWBQwv)

## Some a11y-related GitHub repos

- [make anything draggable and editable](https://github.com/hchiam/draggable)
- [Keyboard focus trap (especially useful for modals)](https://github.com/hchiam/keyboard-focus-trap)

## Some GitHub projects I updated to be more accessible

- [Codepen full page link](https://github.com/hchiam/codepen-full-page-link)
- [Simplified slides editor/presenter](https://github.com/hchiam/slides)
- [My personal CSS boilerplate](https://github.com/hchiam/css-boilerplate)

## Caption file formats

### Basic

- [SubRip (.srt)](https://en.wikipedia.org/wiki/SubRip#SubRip_text_file_format)
- [SubViewer (.sub or .sbv)](https://wiki.videolan.org/SubViewer)
- [LRC (.lrc)](https://en.wikipedia.org/wiki/LRC_%28file_format%29)

### Advanced

- [WebVTT (.vtt)](https://w3c.github.io/webvtt/) <-- easily customizable caption settings on the operating system level and consistent across all WebVTT videos in supported browsers
- [SAMI (.sami or .smi)](https://docs.microsoft.com/en-us/windows/win32/wmp/adding-closed-captions-to-digital-media?redirectedfrom=MSDN)
- [TTML (.ttml)](https://www.w3.org/TR/ttml1/)

## Media Accessibility Decision Matrix (WCAG Level AA "Must"s)

Reference: <https://codepen.io/cerovac/full/MWKVVYj>

Consider: <https://ableplayer.github.io/ableplayer/>

| Media                   | Captions | Transcript | Audio Descriptions | Sign Language |
| ----------------------- | -------- | ---------- | ------------------ | ------------- |
| Pre-recorded Multimedia | Must (C) |            | Must (AD)          |               |
| Pre-recorded Video-only |          |            | Must (AD)          |               |
| Pre-recorded Audio-only |          | Must (T)   |                    |               |
| Live Multimedia         | Must (C) |            |                    |               |
| Live Video-only         |          |            |                    |               |
| Live Audio-only         |          |            |                    |               |

"CAST": C = Captions. AD = Audio Descriptions. T = Transcript. S = Sign Language.

**Mnemonic, version 1:** Just what's AA "Must":

- Pre-recorded Multimedia = CAD.
- Pre-recorded Video-only = AD.
- Pre-recorded Audio-only = T.
- Live Multimedia = C.

**Mnemonic, version 2:** Just letters:

- PMCAD. PVAD. PAT. LMC.

**Mnemonic, version 3:** Semantic overlap:

- Pre-recorded has higher requirements than not pre-recorded.
- Except Multimedia always requires C (whether pre-recorded or not).
- Pre-recorded requires AD if has Video (so Multimedia counts). "See --> Hear".
- Pre-recorded requires T only if Audio-only. "Hear --> See". (Caption naturally doesn't make sense in this case, so must use T.)

**Mnemonic, version 4:** Semantic overlap, reworked: _"Pre-recorded + Multi, Video then AD, Audio then C"_.

- "Pre-recorded + Multi": Only Pre-recorded things have "Must", except Multimedia also always requires Captions (whether pre-recorded or live).
- "If Video then AD": Pre-recorded Video or Multi-media (which contains video) require Audio Descriptions.
- "If Audio then C, except T for Audio-only": Pre-recorded Audio requires Captions, except Audio-only requires Transcript instead (which is similar to Captions), because there's no video to sync the Captions with.

**Note:** It's better to always include a transcript to give access to people who are deafblind, but it also helps with text searches, or if prefer reading quickly over watching.

**Note:** Some people understand a sign language better than captions or transcripts.
