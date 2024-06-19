# Learning Web Accessibility (a11y)

Just one of the things I'm learning. https://github.com/hchiam/learning

This repo's link is easier to remember/type. It serves as a redirect to find this repo faster:

https://github.com/hchiam/web-accessibility-course-notes

Start with the above link. Extra notes may be added to this repo too.

Deque prep course for IAAP WAS: https://dequeuniversity.com/curriculum/packages/iaap-was

## Key things

1. Automate what you can: [WAVE](https://wave.webaim.org/extension) or [axe DevTools for Firefox](https://addons.mozilla.org/en-US/firefox/addon/axe-devtools) or lighthouse or [axe DevTools for Chrome](https://chrome.google.com/webstore/detail/axe-devtools-web-accessib/lhdoppojpmngadmnindnejefpokejbdd) or [axe-linter VSCode extension](https://marketplace.visualstudio.com/items?itemName=deque-systems.vscode-axe-linter).
2. Test realistically: [screen readers](https://www.youtube.com/watch?v=5R-6WvAihms&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g&index=7) + keyboard. Besides mouse and touch. And mobile.
3. Tab. Shift+Tab. Enter. (And screen reader + arrow keys.)
4. Resize page zoom to look for text reflow/overflow bugs.
5. Checklist/report generator: [WCAG-EM](https://www.w3.org/WAI/eval/report-tool)
6. WCAG checklist: https://www.a11yproject.com/checklist or https://www.w3.org/WAI/WCAG22/quickref/?versions=2.1 although you might just want to use the WCAG-EM instead anyways for reporting

## [P.O.U.R.](https://www.w3.org/WAI/WCAG21/Understanding/intro#understanding-the-four-principles-of-accessibility)

My summary:

- P = Perceivable = can see/hear/feel (like captions).
- O = Operable = can use (like element focusability + keyboard + time + recovery).
- U = Understandable = can get meaning (like labels + layout familiarity + meaningful error messages), basically need P and O first before U.
- R = Robust = is flexible/cross-compatible (like mobile versus desktop).

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
- Accessible link that opens in new window: (note that using an HTML-only solution instead of CSS `::before`/`::after` `content` basically guarantees compatibility across browser/screen reader combos especially [CSS `content` for IE](https://jhalabi.com/blog/before-after-accessibility))
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
- [MathJax example](https://codepen.io/hchiam/pen/WNpgzMe)
- [Support Both Legacy JS and Modern JS Without Slowing All Browsers](https://codepen.io/hchiam/pen/mdWGLNE)
- [Deque ARIA patterns CSS+JS](https://codepen.io/hchiam/pen/ExWedQx)

## [COGA (Cognitive Accessibility) guidance](https://www.w3.org/TR/coga-usable/#summary)

- key points = 8 topics: https://www.w3.org/TR/coga-usable/#summary
- user stories
- design guide
- usability testing
- example personas

**The 8 topics are:**

1. Help users understand what things are and how to use them.
2. Help users find what they need.
3. Use clear content (text, images and media).
4. Help users avoid mistakes.
5. Help users focus.
6. Ensure processes do not rely on memory.
7. Provide help and support.
8. Support adaptation and personalization.

## More notes:

<details>
<summary>More notes (click to expand)</summary>

## Random note

Creating instances of elements in JS instead of hidden in HTML will work for getting HTML5 elements to work in IE <= 8 (need instance created first for some reason).

Literally paste the following [Internet Explorer conditional comment](https://stackoverflow.com/a/41430464):

```html
<!--[if lt IE 9]>
  <script>
    var e = (
      "abbr,article,aside,audio,bdi,canvas,datalist,details,dialog," +
      "figcaption,figure,footer,header,keygen,mark,menu,meter,main,nav,output," +
      "progress,rp,ruby,rt,section,source,summary,time,track,video,wbr"
    ).split(",");
    for (var i = 0; i < e.length; i++) {
      document.createElement(e[i]);
    }
  </script>
<![endif]-->
```

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

Reference: https://codepen.io/cerovac/full/MWKVVYj

Consider: https://ableplayer.github.io/ableplayer/

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
- Move focus to new content only if triggered by user (example: modal), otherwise it's disorienting (example: screen reader users tend to explore forms before filling them out, triggering blur).
- Move focus to next logical element if element removed (example: closing modal). This means you need to maintain the previously-focused element in memory somehow. (Otherwise focus returns to top of page - really bad.) Also make sure the re-focused element announces something so the user knows what they teleported to.
- Widget usage instructions with a popup tooltip + aria-label are nice to have when focusing on a custom widget or when users aren't familiar with the standard ARIA keyboard interaction patterns for a widget.
- Make infinite scrolling the last element on the page, or let users "escape", or let users decide to load more.
- You can use `tabindex="-1"` on text to let JS focus it, otherwise `tabindex="0"` might confuse users when they happen to focus it with Tab (when they expect the usual focusable elements).

## Notes on touch input

- Make sure gestures can also be alternatively done with taps (for people with mobility/dexterity issues having difficulty performing touch gestures).
- A click event is accessible to mouse **_and_** touch **_and_** keyboard! (As opposed to `onmouseup` or `ontouchend` or `onkeyup`.)

## Notes on forms

- `aria-describedby` won't work on `<fieldset>` or `<legend>`, so avoid having _non-label/non-focusable_ text in the middle of a form (users likely will tab and miss the text), and instead put the text before the form, or associate the text with one or more of the inputs with `aria-describedby` on them.
- Make sure instructions and labels are _next to_ their related inputs (both visual and cognitive effects). Otherwise they can be hidden/shown with a button, _instead of_ making the text small.
- Tell screen reader users of required fields with `aria-required="true"`. The alternative is the `<... required>` attribute, which adds browser behaviour, but does so inconsistently, and may conflict with your custom form validation behaviours. Either way, also include visual indicators for sighted users.
- `aria-invalid="true"` and `aria-describedby="error_description"` on the inputs
- `<a href="#email">Go to the first field with an error to fix it.</a>`
- `autocomplete="current-password"` - see https://www.w3.org/TR/WCAG21/#input-purposes
- Example: https://dequeuniversity.com/assets/html/module-forms/progressive/good/index.html
- Custom form element: make sure it has a Name, Role, and Attribute (i.e. Label, Role, and State.). Anything that can't be communicated via those things should go into an `aria-live` region.
- Confirm before submitting (and enable fixing).
- Confirm after submitting (set focus _after_ page load to avoid issues with parsing timing).
- Consider indicating form success/error in `<title>` = first thing user hears on new page.
- Consider `aria-live` with 2-second debounce for "password strength messages". (On blur won't work because the new focus will likely get announced instead.)
- Tab, Shift + Tab, Enter/Spacebar, arrow keys, (for `<select>`:) Alt/Option + Down arrow and then arrow keys and then Enter

## Notes on screen readers

- [Common screen readers and common keyboard shortcuts for them](https://dequeuniversity.com/assets/pdf/screenreaders/screen-readers-commands.pdf).
- Test dynamic content with at least 2 screen readers, since there can be big differences in how they handle dynamic content.
  - And don't forget about different browser combinations.
  - And mobile TalkBack (Android) and VoiceOver (iOS).
  - There are screen reader survey stats (2019) on [primary screen reader](https://webaim.org/projects/screenreadersurvey8/#primary) and [screen reader usage](https://webaim.org/projects/screenreadersurvey8/#used) and [primary browser](https://webaim.org/projects/screenreadersurvey8/#browsers) and [screen reader + browser combos](https://webaim.org/projects/screenreadersurvey8/#browsercombos) and [OS](https://webaim.org/projects/screenreadersurvey8/#os) and [mobile](https://webaim.org/projects/screenreadersurvey8/#mobile) and [headings vs find](https://webaim.org/projects/screenreadersurvey8/#finding) and [multi-language use](https://webaim.org/projects/screenreadersurvey8/#language).
- suggested screen reader + browser/device combos:
  - [JAWS](https://www.freedomscientific.com/products/software/jaws/) with Chrome/IE
  - [NVDA](http://www.nvaccess.org/download/) with Firefox/Chrome
  - Narrator with Edge
  - VoiceOver with Safari (macOS)
  - VoiceOver with Safari (iOS)
  - TalkBack with Chrome (Android)
- Most screen readers can automatically or manually switch between different modes depending on context, to let you type extra or different commands to do things useful in context: document/reading mode, table mode, forms mode, app mode, virtual cursor mode, focus mode, etc. For example, you wouldn't want the next header key shortcut H to trigger when typing the letter H into a form input. Modes switch automatically in VoiceOver.
- JAWS seems to cover the most browsers, _including IE_. It also has cursor options. But [JAWS is expensive](https://sheribyrnehaber.medium.com/accessibility-best-practices-for-screenreader-testing-e35c5df9cecb). So NVDA seems best to me to use, especially with the [rise in popularity of NVDA](https://webaim.org/projects/screenreadersurvey8/#used).
- JAWS works well with Chrome, Firefox, Edge, and IE.
- NVDA works well with Chrome, Firefox, and Edge. But NVDA has recently gained more popularity than JAWS ([2019 screen reader survey](https://webaim.org/projects/screenreadersurvey8/#primary)).
- Narrator works best with Edge. It also has a Developer mode that lets you see only the things currently exposed to the screen reader.
- VoiceOver works best with Safari.
- [ChromeVox](https://support.google.com/chromebook/answer/7031755) works on Chrome and ChromeOS/Chromebooks.
- Consider telling users that content is still loading with things like `alt="Content loading"` (but don't go overboard with `aria-live` unless it's a really slow process).
- Using `visibility: hidden;`, `display: none;`, or attribute `hidden` will hide the element visually but also hides it from screen readers, so you'll need to resort to clipping or positioning or `aria-label` to expose it to screen readers only. See my notes on [hiding elements visually and/or in the Accessibility Tree](https://github.com/hchiam/web-accessibility-course-notes#hidingshowing-only-for-accessibility-tree-at).

- ```css
  /* source: https://webaim.org/techniques/css/invisiblecontent/ */
  .sr-only {
    /* screen-reader-only: */
    clip: rect(1px, 1px, 1px, 1px);
    clip-path: inset(50%);
    height: 1px;
    width: 1px;
    margin: -1px;
    overflow: hidden;
    padding: 0;
    position: absolute;
  }
  ```

## Notes on new content or SPAs (Single-Page Apps)

- "Please wait" message (or new content for SPAs): focus on it or `aria-live` it. Plan some shared method to manage focus or to announce link/route events. Consider intentional pause before resetting focus, in case the delay is shorter than expected (consider "Please wait. Here's some content that already loaded but sounds like part of the interstitial message.") and to avoid timing issues.
- In VoiceOver, focus needs to be (re)sent to an element for it to be announced, even if its text changed (so temporarily send focus to an empty container and back).

  ```js
  event.preventDefault();

  hiddenEmptyContainerForTemporaryFocus.focus(); // <--- to enable announcing the later-focused element in case it happens to be the same element but updated

  oldContent.empty();
  populateNewContent();

  updateBrowserHistory(newUrl, newTitle); // <--- for SPAs

  var delayForIOS = 1000;
  setTimeout(() => {
    newHeading.focus(); // <--- to orient the teleported user
  }, delayForIOS);
  ```

- For SPA links: remember to systematically update browser history so the back button works.

  ```js
  function updateBrowserHistory(newUrl, newTitle) {
    history.pushState(
      {
        url: newUrl,
        title: newTitle,
      },
      newTitle,
      newUrl
    );
  }
  ```

  ```js
  $(window).on("popstate", function (event) {
    var state = event.originalEvent.state;
    var wasBackOrForwardHit = state !== null;
    if (wasBackOrForwardHit) {
      oldContent.empty();
      document.title = state.title; // screen reader will read <title> first (good place for status update)
      populateNewContent();
      var delayForIOS = 1000;
      setTimeout(() => {
        newHeading.focus();
      }, delayForIOS);
    }
  });
  ```

## Notes on accessible name calculation algorithm

### Basically

1. `aria-labelledby` (Note: this is **_NOT_** `aria-labelledby`.)
2. `aria-label`
3. text <-- (but for implementation, go for this option first)
4. (`title` but only kinda works for some users)

### Fun facts

- Note that description !== label.
- Label = replaces the element's original text.
- Description = (with a pause) announced after the computed label, as extra info.
- `aria-labelledby="can have multiple IDs as labels"`
- Keep in mind that `aria-label` is not consistently supported for some non-focusable elements, screen reader versions/modes, or browser versions.
- Use `aria-label` on the search box, since it's usually focused before the button, otherwise it's not immediately obvious what the `input` is for:

  ```js
  <form action="#" role="search">
    <input aria-label="Search" name="search" type="search">
    <input type="submit" value="Search">
  </form>
  ```

## Note on visual disabilities

- note: bigger text is not necessarily always better, e.g. people with "tunnel vision" may prefer small font and tighter line spacing - https://learning.edx.org/course/course-v1:W3Cx+WAI0.1x+3T2019/home - take-away: flexibility!

## Note on physical impairments

- note: let users disable/customize single-key keyboard shortcuts to avoid voice-only users accidentally triggering multiple keyboard shortcuts with one word of a voice command (aside from self: getting surprised by keyboard shortcuts I didn't expect to exist or want to trigger) - https://learning.edx.org/course/course-v1:W3Cx+WAI0.1x+3T2019/home - take-away: flexibility!

## Notes on screen magnification

- from https://learning.edx.org/course/course-v1:W3Cx+WAI0.1x+3T2019/home
  - screen changes in other parts of the page should still be notified to screen magnification users
  - key content should not be contained in hover states or tooltips, especially if it's hard for screen magnification users to see on-screen
  - position priority content where users expect it

## Note on page titles (browser tab title)

- note: "front-load" when you can, i.e. unique and most important info first (think: what shows up in the browser tab, to keep it unique) - https://learning.edx.org/course/course-v1:W3Cx+WAI0.1x+3T2019/home

## Note on `disabled` buttons and inputs

- [css-tricks](https://css-tricks.com/making-disabled-buttons-more-inclusive/) recommends `aria-disabled="true"` and JS to prevent clicks by pointers or keyboards
- but I'd consider this jQuery helper function I wrote: ([demo of `disableEditing`](https://codepen.io/hchiam/pen/jOoZZEW?editors=1010))
  ```js
  /**
  Don't disable submit button (screenreader user: unaware skipped; sighted user: must realize must hunt for errors).  
  Don't disable inputs like textareas or select dropdowns: screen readers can't tab to it to read the value!
  TODO: make this work for radios and checkboxes
  */
  function disableEditing(scope, isEditDisabled) {
      const elements = $(scope.is(':input') ? scope : $()).add(scope.find(':input'));
      elements
          .removeAttr('disabled').prop('disabled', false) // to enable tab focus
          .prop('readonly', isEditDisabled) // to disable edits without disabling focus
          .attr('edit-disabled', ''); // to disable clicks
      elements.find('option')
          .toggle(!isEditDisabled); // to prevent showing and changing select dropdown options
  }
  var scope = $('.modal:visible :input:disabled');
  editDisabled(scope, true);
  ```

## Notes on ARIA roles

- Ctrl+F or Cmd+F for ARIA roles and ARIA attributes in this [Role Data Model](https://www.w3.org/TR/wai-aria/img/rdf_model.svg)
  - On top: ARIA roles. Example: `role="checkbox"`.
  - On bottom: ARIA attributes. Example: `aria-checked="true"`. (Link: [descriptions of ARIA attributes](https://www.w3.org/TR/wai-aria/#global_states))
  - (Note: some roles are "abstract" and can't actually be used in the code.)
- Only use ARIA roles+attributes if you need to. Better to use native built-ins.
- For modals, you'll likely need to put `role="document"` to wrap the text content like `<p>` etc. when the modal container has `role="dialog"`. This is because `role="dialog"` turns some screen readers to application mode (basically inherits `role="application"`), which ignores text that doesn't have `tabindex="0"` set, so you may need `role="document"` to turn those screen readers back to document mode. `<div role="dialog"><div role="document">`.
- `role="application"` gives developers more freedom but also more responsibility. It turns off most page navigation features, which lets you define custom keyboard logic, but now you might need to re-implement a bunch of things.

  - Notably, application mode does not turn off the normal behaviour of: Tab for focus, Enter/Return, space bar, or arrow keys (on selects or radios).

  - So you sometimes might need to do this: (unless you set `tabindex="0"` on text elements, which may mislead users to think they're on buttons)

  ```html
  <div role="application">
    <div role="document"></div>
  </div>
  ```

  - `role="dialog"` and `role="alertdialog"` and `role="tablist"` automatically trigger application mode and hence keyboard limitations/freedoms.

- You can use `role="math"` and `aria-label="(description of the math expression)"` on a `<div>` that wraps MathML markup with a `<math>` element, but MathML isn't universally supported. Or just use MathJax, which also happens to be able to help with MathML markup support for all browsers.
  - [MathJax example](https://codepen.io/hchiam/pen/WNpgzMe)
- `aria-busy="true"` if you want to suppress suppress `aria-live` region announcements (e.g. page load).

- tabs:
  - `role="tablist"` contains `role="tab"` which controls display of `role="tabpanel"`
  - `aria-selected="true"` the current tab (`role="tab"`)

## Deque ARIA patterns

1. Alert
2. Current page: Button
3. Button (Toggle)
4. Carousel (based on a tabpanel)
5. Checkbox
6. Checkbox (Tri-State)
7. Dialog (Simple Dialog)
8. Dialog (Simple Alert Dialog)
9. Dialog (Message Dialog)
10. Dialog (Message Alert Dialog)
11. Expand/Collapse
12. Expand/Collapse (based on Details/Summary)
13. Link
14. Navigation (Hierarchical) with Expand/Collapse
15. Predictive Text
16. Progress Bar (Bounded)
17. Progress Bar (Unbounded)
18. Radio and Radio Group
19. Slider
20. Slider (Multirange)
21. Tabpanel
22. Table (Responsive, Collapsible)
23. Table (Sortable)
24. Tooltip
25. Tooltip Dialog
26. Tree View

### Deque ARIA patterns - Imports

- CSS: `<link rel="stylesheet" href="https://dequeuniversity.com/assets/js/patterns/deque-patterns.min.css">`
- JS: `<script src="https://dequeuniversity.com/assets/js/patterns/deque-patterns.min.js"></script>`
- Fonts: https://dequeuniversity.com/assets/js/patterns/_fonts/MWFMDL2.1.63.ttf and https://dequeuniversity.com/assets/js/patterns/_fonts/MWFMDL2.1.63.woff

### Deque ARIA patterns - Examples

- https://codepen.io/hchiam/pen/gOmdBBo
- https://codepen.io/hchiam/pen/ExWedQx

## Analogy for Accessibility Tree element properties

- Name: `aria-label="Howard"`
- Description: `aria-description="likes learning"` or `aria-describedby="description_container_id"`
- Role: `role="software developer"`
- Property: `start="9" end="5"` (and value)
- Relationship: `aria-owns="this GitHub account"`
- State: `aria-selected="true"`

## WCAG notes

- "PGS": 4 Principles --> Guidelines --> SC (Success criteria) --> A, AA, AAA.

## WCAG-EM notes

- WCAG-EM = [website accessibility conformance evaluation methodology](https://www.w3.org/WAI/test-evaluate/conformance/wcag-em/)
- [WCAG-EM procedure](https://www.w3.org/TR/WCAG-EM/#procedure)
- [WCAG-EM report generator](https://www.w3.org/WAI/eval/report-tool)

  - Very helpful form! Reminders of all the steps! Auto-adjusts field prompts depending on selected A/AA/AAA level!
  - Steps: "S.E.S.A.R.":
    1. Scope (prioritize, images, forms, tables, widgets, consider to-be-commonly-used templates)
    2. Explore (automated test to cover 30%, then screen reader + browser + device combos)
    3. Sample
    4. Audit sample
    5. Report (say what bug, where, what expect, what breaks for who, how impactful on user+/business+/design-, how repro, visual, how might fix, how easy to fix) = faster to triage and actually fix

- another way to break down the 9 things in the Report:
  1. what
  2. where
  3. who
  4. what expect
  5. how impactful (user, business, design)
  6. how might fix
  7. how easy fix
  8. visual
  9. how repro

## Various terms to know

Test yourself:

- a11y
- UX
- POUR
- W3C
- WCAG
- WAI-ARIA
- ATAG
- WCAG-EM
- A, AA, AAA
- ADA
- Section 508
- WCAG 2.1
- CVAA
- AODA
- EN 301 549
- IAAP
- WAS
- CPACC
- AT
- JAWS
- NVDA
- WAVE
- WebAIM
- Deque
- BOK
- SC

<details>
<summary>Answers</summary>

- accessibility
- user experience
- perceivable, operable, understandable, robust (can you explain each in simple words, and give an example?)
- world wide web consortium (standards org)
- web content accessibility guidelines (practical)
- web accessibility initiative - accessible rich internet applications (HTML attributes spec to add semantics)
- authoring tool accessibility guidelines
- website accessibility conformance evaluation methodology
- lowest, mid range, highest (usually go with AA)
- americans with disabilities act (civil, US)
- government procurement rules (US)
- recent update to WCAG
- 21st century communications and video accessibility act (US, communications must be accessible, like TV for example)
- accessibility for ontarians with disabilities act (civil, like ADA)
- EN 301 549 is government procurement rules (Europe) (like Section 508)
- international association of accessibility professionals
- web accessibility specialist
- certified professional in accessibility core competencies
- accessibility tree
- job access with speech
- nonvisual desktop access
- web accessibility evaluation tool
- web accessibility in mind
- deque = Deque Systems
- body of knowledge
- success criteria

</details>

## Policy examples and templates for your company

- simple: https://www.w3.org/WAI/planning/org-policies/#examples

- comprehensive: https://www.w3.org/WAI/planning/org-policies/example/

## Accessibility statement generator

- https://www.w3.org/WAI/planning/statements/generator/#create
  - minimal example: https://www.w3.org/WAI/planning/statements/minimal-example/
  - complete example: https://www.w3.org/WAI/planning/statements/complete-example/
- consider including:
  - commitment
  - contact info for issues
  - known limitations (to avoid frustrations)
  - measures to ensure accessibility
  - technical requirements like supported browsers
  - environments tested to work in
  - references to applicable local and national laws and policies

</details>
