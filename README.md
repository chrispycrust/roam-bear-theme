# Bear Pro themes for Roam: solarised light and charcoal

Note-taking experiences should be pleasurable. I like these themes generally because they're more low contrast than others and I tend towards warmer tones. High contrast colours are sharper, more stark and will hurt more especially when viewing content at night. rcvd's night bear theme for logseq is like this. 

Viewed on Microsoft Edge

## Light theme: Solarised Light

![Solarized Light theme screenshot](solarised-light-theme.png "Solarized Light theme in Roam")

## Dark theme: Charcoal

![Charcoal theme screenshot](charcoal-dark-theme.png "Charcoal dark theme in Roam")

I slightly modified the original bear colours for charcoal e.g. upping saturation for acccent which i've used for reference pages and links so it's more easily differentiated.

## to-dos

- ### adjustments to increase readability and ease of use 
    - viewed at 100%, the font is way too small, i have to zoom to 150% manually in browser to get to a more comfortable reading size
    - the colour of the pop up hover on charcoal needs to be adjusted as it can conflict with other sections with similar coloured background e.g. within section of linked refs
    - search bar results: no hover styling, formatted in a way that we're unable to see properly
    - heading/page titles: unable to target textarea when editing to get it consistent, so it's switching between serif display and avenir sans-serif when editing, pretty annoying
    - tags: disable line-wrap? looks awkward when a background is applied
    - "unlinked reference" title is too bright in dark theme and off-colour in solarised light, seems to be styled separately from "linked reference", not what I expected
    - caret fix: erratic flickering between colour i've defined and black in code block.. instead of between caret colour and transparent. i've identified these following classes
        ```
        .rm-inline-code-block,
        .ͼ2 .cm-content,
        .ͼ4 .cm-line {
            caret-color: red !important;    
        }
        ```
    - want to fix alignment of large headings to the bullet point, but actually aligns to baseline ref blocks and center of blockquotes 
        ```
        .roam-block-container .rm-block-main { 
            align-items: baseline;
        }
        ```
    - want to add more breathing room above "Unlinked references" but targeting `.flex-h-box` also affects some sidebar items
        ```
        .flex-h-box {
            padding-top: 10px;
        }
        ```
    - test on different browsers. firefox seems to make the fonts thicker instead of fine, also adds its own scrollbar which doesn't fit the theme

- ### adjustments for theme consistency
    - "All Pages" title - adjust table heading colours
    - adjust the highlight colour for solarised theme - it's lighter and more desaturated in the actual Bear app #f0e8d0 => hsl(45 52% 88%)
    - change colour of border when bullet is expanded 
    - change colour of checkmark when completed to match theme
    - highlighting a complete code block (with all nested elemenets if there are any) is different to highlighting within a code block. it's a deep blue. how to target to change??
    - bullet border colour in sidebar seems to be different than border in the main app area

- ### other adjustments
    - subtle border change when focussing a search text area
    - there's a more noticeable fade when hovering over each navigation item in left sidebar in logseq
    - disable background change when hovering over roam research - or expand clickable area, looks bad that square chunk, and it doesn't transition properly ... may be coded separately from the others, potentially hard coded into html with "style" property

## extra stuff to add

- incorporate some of the subtle animations in logseq which increases overall feel of responsiveness
    - e.g. on hover over a bullet, a border appears and the bullet itself expands larger even if there's no nested content
    - hovering over a checkbox adds a border in the dark theme, in the light theme, it seems like it's slightly expanding 
- ticking a checkbox is accompanied by a strikethrough, much more easily differentiated. the strikethrough is also the colour of the accent
- caret 
    - change shape of code blocks to underscore or block to mimic typing on the terminal xD 
    - can we make the caret thicker and more noticeable? maybe use block but influence the block? in bear it seems to be longer than the line-height (or it is at line height?) and it's maybe 2-3px thick? the default caret is so thin
- tag background should be fatter - try increasing line-height so they don't cut into each other
- replacing bullet-points with icons from https://tabler-icons.io/ like nmartin84: https://github.com/nmartin84/logseq-flow
- automatically switch from light to dark theme as scheduled with user's system and correspond with the light and dark switch in the UI
- query for "on this day" embedded into each journal entry https://unofficial-logseq-docs.gitbook.io/unofficial-logseq-docs/beginner-to-advance-features/on-this-day-query-page
- some styling for certain elements like roam research logo are hardcoded into the html page under "style" attribute. could be possible to swap this out or influence the look with JS??
- want to make every even row of table on "All Pages" a different colour 
    ```
    .rm-all-pages .table .rm-pages-row.rm-pages-row-header {
        background-color: ;
        color: ;
    }
    ```
- changing hover effect of links and tags, not a fan of text underline as it's too close to the words. targeting the hover pseudo-selec both normal links and tags 
    ```
    .rm-page-ref:hover { 
        text-decoration: none;
    }
    ```
- reproduce olive theme from Bear for fresher feel

## What I've learnt from trying to code my own theme

- investigating how to properly sync Git, GitHub, and GitHub Desktop
- utilising css variables
- familiarising myself with devtools and reading through someone else's code, understanding it enough to make my own modifications
- getting to see a bit more into the inner workings of roam - a software i use daily
- paying attention to the details in someone else's design (Bear Pro themes) and translating it another context, playing around with what works and what doesn't
- documentation and keeping progress. getting more familiar with using markdown for notes to self and documentation, striving for better commit summaries on github not for your own sake but others when working in teams