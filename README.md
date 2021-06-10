# Learning accessibility (a11y)

Just one of the things I'm learning. <https://github.com/hchiam/learning>

This repo's link is easier to remember/type. It serves as a redirect to find this repo faster:

<https://github.com/hchiam/web-accessibility-course-notes>

Start with the above link. Extra notes may be added to this repo too.

Deque prep course for IAAP WAS: <https://dequeuniversity.com/curriculum/packages/iaap-was>

## Key things I personally focus on most

1. Use [WAVE](https://chrome.google.com/webstore/detail/wave-evaluation-tool/jbbplnpkjmmeebjpijfedlgcdilocofh) or some other automated a11y checker, like [axe DevTools for Firefox](https://addons.mozilla.org/en-US/firefox/addon/axe-devtools) or lighthouse or [axe DevTools for Chrome](https://chrome.google.com/webstore/detail/axe-devtools-web-accessib/lhdoppojpmngadmnindnejefpokejbdd).
2. Use a [screen reader](https://www.youtube.com/watch?v=5R-6WvAihms&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g&index=7). Test as realistically as possible.
3. Tab. Shift+Tab. Enter. (And screen reader + arrow keys.)

## P.O.U.R.

My summary:

- P = Perceivable = can see/hear/feel (like captions)
- O = Operable = can use (like element focusability + keyboard + time + recovery)
- U = Understandable = can get meaning (like labels + layout familiarity + meaningful error messages)
- R = Robust = is flexible/cross-compatible (like mobile versus desktop)

## Some a11y-related GitHub repos

- [make anything draggable and editable](https://github.com/hchiam/draggable)
- [Keyboard focus trap (especially useful for modals)](https://github.com/hchiam/keyboard-focus-trap)

## Some GitHub projects I updated to be more accessible

- [Codepen full page link](https://github.com/hchiam/codepen-full-page-link)
- [Simplified slides editor/presenter](https://github.com/hchiam/slides)
- [My personal CSS boilerplate](https://github.com/hchiam/css-boilerplate)

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
- [accessible form (group label)](https://codepen.io/hchiam/pen/GRWXjZK)

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

## Notes on parallax

- Parallax scrolling can decrease usability or even cause dizziness in some people (e.g. those who have vestibular disorders).
- CSS media query `prefers-reduced-motion` is currently not universally supported, so consider a including a setting toggle for now, as long as functionality/access is preserved without the removed animations.

## Notes on mouse input

- Up event (not on down event) = cancellable before release.
- Consider click target size. (For mobile: 44px squared or 48px squared min.)
- A click event is accessible to mouse **_and_** touch **_and_** keyboard! (As opposed to `onmouseup` or `ontouchend` or `onkeyup`.)

## Notes on focus

- System-wide keyboard accessibility: Mac has a setting that lets you tab to all controls, not just inputs.
- Move focus to new content triggered by user (example: modal), otherwise it's disorienting (example: screen reader users tend to explore forms before filling them out, triggering blur).
- Move focus to next logical element if element removed (example: closing modal). This means you need to maintain the previously-focused element in memory somehow. (Otherwise focus returns to top of page - really bad.) Also make sure the re-focused element announces something so the user knows what they teleported to.
- Widget usage instructions with a popup tooltip + aria-label are nice to have when focusing on a custom widget or when users aren't familiar with the standard ARIA keyboard interaction patterns for a widget.
- Make infinite scrolling the last element on the page, or let users "escape", or let users decide to load more.

## Notes on touch input

- Make sure gestures can also be done with taps (for people with mobility issues).
- A click event is accessible to mouse **_and_** touch **_and_** keyboard! (As opposed to `onmouseup` or `ontouchend` or `onkeyup`.)

## Notes on forms

- `aria-describedby` won't work on `<fieldset>` or `<legend>`, so avoid having _non-label/non-focusable_ text in the middle of a form (users likely will tab and miss the text), and instead put the text before the form, or associate the text with one or more of the inputs with `aria-describedby` on them.
- Make sure instructions and labels are _next to_ their related inputs (both visual and cognitive effects). Otherwise they can be hidden/shown with a button, _instead of_ making the text small.
- Tell screen reader users of required fields with `aria-required="true"` (or `<... required>` which adds browser behaviour, but does so inconsistently, and may conflict with your custom form validation behaviours). Either way, also include visual indicators for sighted users.
- `aria-invalid="true"` and `aria-describedby="error_description"` on the inputs
- `<a href="#email">Go to the first field with an error to fix it.</a>`
- `autocomplete="current-password"` - see <https://www.w3.org/TR/WCAG21/#input-purposes>
- Example: <https://dequeuniversity.com/assets/html/module-forms/progressive/good/index.html>
- Custom form element: make sure it has a Name, Role, and Attribute (i.e. Label, Role, and State.). Anything that can't be communicated via those things should go into an `aria-live` region.
- Confirm before submitting (and enable fixing).
- Confirm after submitting (set focus _after_ page load to avoid issues with parsing timing).
- Consider indicating form success/error in `<title>` = first thing user hears on new page.
- Consider `aria-live` with 2-second debounce for password strength. (On blur won't work because the new focus will likely get announced instead.)
- Tab, Shift + Tab, Enter/Spacebar, arrow keys, (for `<select>`:) Alt/Option + Down arrow and then arrow keys and then Enter

## Notes on screen readers

- Most screen readers can automatically or manually switch between different modes depending on context, to let you type extra or different commands to do things useful in context: document/reading mode, table mode, forms mode, app mode, virtual cursor mode, focus mode, etc. For example, you wouldn't want the next header key shortcut H to trigger when typing the letter H into a form input. Modes switch automatically in VoiceOver.
- JAWS seems to cover the most browsers, _including IE_.
- JAWS works well with Chrome, Firefox, Edge, and IE.
- NVDA works well with Chrome, Firefox, and Edge.
- Narrator works best with Edge.
- VoiceOver works best with Safari.
- ChromeVox works on Chrome.
- Consider telling users that content is still loading with things like `alt="Content loading"` (but don't go overboard with `aria-live` unless it's a really slow process).
- "Please wait" message: focus on it or `aria-live` it. Intentionally pause before resetting focus, in case the delay is shorter than expected (consider "Please wait. Here's some content that already loaded but sounds like part of the interstitial message.").
