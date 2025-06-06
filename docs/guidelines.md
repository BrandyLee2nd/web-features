# Feature guidelines

## Names

The `name` field contains the feature's human-readable plain-text name.

Feature authors should (in descending order of priority):

- Prefer names known to be in widespread use by web developers.
  Favor describing things as they are most-widely known, even if it's not the most technically correct option.

  - 👍 Recommended: JavaScript
  - 👎 Not recommended: ECMAScript
  - 👍 Recommended: Declarative shadow DOM
  - 👎 Not recommended: `shadowrootmode` attribute

- Avoid prefixes that mark a feature as specific to a technology, such as CSS, HTML, or JavaScript.
  Features can and do cross such boundaries.

  - 👍 Recommended: Container queries
  - 👎 Not recommended: CSS container queries
  - 👍 Recommended: `<dialog>`
  - 👎 Not recommended: HTML `<dialog>`

- Avoid frequently-used abbreviations and nouns, such as API and Web.

  - 👍 Recommended: Async clipboard
  - 👎 Not recommended: Async clipboard API
  - 👍 Recommended: Workers
  - 👎 Not recommended: Web workers

- Prefer common, descriptive noun phrases over abbreviations, metonymy, and syntax.

  - 👍 Recommended: Offscreen canvas
  - 👎 Not recommended: `OffscreenCanvas`
  - 👍 Recommended: Grid
  - 👎 Not recommended: `display: grid`

- Prefer sentence case.
  Avoid capitalizing ordinary nouns, but preserve case when it's meaningful.

  - 👍 Recommended: Typed arrays
  - 👎 Not recommended: Typed Arrays
  - 👍 Recommended: View transitions
  - 👎 Not recommended: View Transitions
  - 👍 Recommended: WebDriver BiDi
  - 👎 Not recommended: Webdriver bidi

- Prefer frequently-used qualifiers in parentheses at the end of the name.

  - 👍 Recommended: Arrays (initial support)
  - 👎 Not recommended: Initial support for arrays

- Prefer shorter names to longer names, as long as they're unique and unambiguous.

  - 👍 Recommended: `:has()`
  - 👎 Not recommended: `:has()` pseudo-class
  - 👍 Recommended: `<dialog>`
  - 👎 Not recommended: `<dialog>` element

## Identifiers

A feature's identifier is the feature's filename before the `.yml` extension.

Feature identifiers must start with a lowercase alphabetic character (a-z) and contain only lowercase alphanumeric characters (a-z and 0-9) plus the `-` character (hyphen or minus sign) as a word separator.

The identifier should match the name, with these additional guidelines:

- Prefer shorter identifiers to longer identifiers, by avoiding common qualifiers and repeated words.

  - 👍 Recommended: `aborting`
  - 👎 Not recommended: `abort-controller-and-abort-signal`
  - 👍 Recommended: `arrays`
  - 👎 Not recommended: `arrays-initial-support`
  - 👍 Recommended: `fullscreen`
  - 👎 Not recommended: `fullscreen-api`
  - 👍 Recommended: `user-pseudos`
  - 👎 Not recommended: `user-valid-and-user-invalid`

## Descriptions

The `description` field contains a short description of the feature in Markdown-formatted text, which is converted to HTML in the published package.
Follow the general writing guidelines in this section, but see the [word and phrase list](#word-and-phrase-list) for specific usage instructions.

* Describe, in the active voice, what a feature does or is.
  Think about how developers will use it, not abstract technology relationships.
  Start with a template like this:

  - `The <property> <sets> the <noun>.`
  - `The <interface> <verbs> the <noun>.`
  - `The <type> represents <nouns>.`
  - `<format> is a <kind> or <variety>`.

* Description text must stand alone.
  It should not refer to text, images, or other content outside the short description.
  Try reading the sentence aloud.
  Does it still make sense without mentioning the name or ID?

* Enclose literal code, such as CSS property names, interface and method names, or other syntax, in backticks.
  For example, prefer ```The `addEventListener()` method…``` and avoid ```The addEventListener() method…```.

* To aid search, include literal text that a web developer would inevitably type if they were to invoke the feature.
  If there's no essential entry point to the feature, then include only concise snippets of essential literal code instead.
  Never use made-up, idiosyncratic, or non-literal example code.

  * 👍 Recommended: `display: flex`, `fetch()`, etc.
  * 👎 Not recommended: `(await navigator.serviceWorker.ready).sync`
  * 👍 Recommended: "`margin-top`, `margin-right`, `margin-bottom`, and `margin-left`"
  * 👎 Not recommended: `margin-{top,right,bottom,left}`

* Start descriptions with words that are distinct to the feature.
  For example, prefer "The `some-prop` CSS property…" and avoid "The CSS property `some-prop`…."

* Avoid circular descriptions.
  For example, prefer "The `filter()` method returns the items…" over "The `filter()` method filters the items…."

* It's OK to use the second person ("you", "your", and "yours") to refer to the audience when needed.
  For example, "The interface allows you to…."
  ([#738](https://github.com/web-platform-dx/web-features/pull/742))

* Never mention support or standards status.
  This information *will* go out of date and sooner than you think.

* For every rule, there's a counterexample.
  Use your best judgement before writing something absurd.

### Word and phrase list

For general usage recommendations not covered by this list, such as word choice or punctuation, refer to the [Microsoft Writing Style Guide](https://learn.microsoft.com/en-us/style-guide/welcome/).

#### allows

OK in usage such as "allows you to…."
Avoid where there is no named actor, as in "the feature allows magic to happen."
([#738](https://github.com/web-platform-dx/web-features/pull/738#discussion_r1537760761))

You can often omit it with gerunds.
For example, prefer "The widget sends…" over "The widget allows sending…."

#### also known as

Use this phrase to call attention to other names this feature has gone by.
Use it at the start of a sentence at the end of the description.
For example:

 > The `some-property` CSS property sets the … value. Also known as `<alias>`.
([#628](https://github.com/web-platform-dx/web-features/pull/628/files/a9898862cb631c83ea16f1233b3c5c4353bf7a52#r1516293423))

#### declaration

For CSS, use _declaration_ to refer to property-value pairs.
For example, prefer "The `some-property: none` CSS declaration…" over The `some-property: none` CSS property value…."
([#969](https://github.com/web-platform-dx/web-features/pull/969))

#### defines

Avoid.
See [sets](#sets).
([#727](https://github.com/web-platform-dx/web-features/pull/727#discussion_r1537635491))

#### determines

Avoid.
See [sets](#sets).
([#727](https://github.com/web-platform-dx/web-features/pull/727#discussion_r1537635491))

#### device

Use "device" to refer to the underlying operating system or hardware environment, or combination thereof.
This is to avoid cumbersome phrases like "the operating system or hardware" or specifically enumerating Linux, macOS, and Windows.
For example, write "the device UI" not the "operating system UI."
([#810](https://github.com/web-platform-dx/web-features/pull/810))

#### elements

Avoid "element" in reference to things that are not HTML elements.
For example, an array of objects has "items", not "elements."
([#750](https://github.com/web-platform-dx/web-features/pull/750#discussion_r1543011420))

#### enables

Avoid, except in the sense of to turn on or activate.
See [allows](#allows).
([#750](https://github.com/web-platform-dx/web-features/pull/750#discussion_r1547382081))

#### for example

Don't use it as a coordinating conjunction; start a new sentence instead.
For example, this is an example.
([#738](https://github.com/web-platform-dx/web-features/pull/738#discussion_r1537762579), [#742](https://github.com/web-platform-dx/web-features/pull/742))

#### is used to

Omit "is used" where there's no loss in meaning.
For example, prefer "The feature reads…" over "The feature is used to read…"
([#727](https://github.com/web-platform-dx/web-features/pull/727#discussion_r1537635981))

#### longhands and shorthands

Use the terms "shorthand" and "longhand" to describe the relationship between CSS properties that combine multiple properties into a single declaration and the individual properties. 

Avoid using "shorthand" and "longhand" without the word "property":

* Prefer "The `text-wrap` CSS property is a shorthand" over "The `text-wrap` CSS shorthand".
* Prefer "It is a longhand property of" over "It is a longhand of".

Avoid the phrase "constituent properties" for longhand properties, even though this is common on MDN Web Docs.
([#1764](https://github.com/web-platform-dx/web-features/pull/1764#discussion_r1777335770))

#### platform

"platform" is often vague.
Avoid using it by itself.
Instead, prefer more complete phrases that make it clear which platform you're referring to, such as "the web platform."

#### provides

Avoid, especially with gerunds.
For example, prefer the "The feature writes to…" over "The feature provides writing to…."
([#727](https://github.com/web-platform-dx/web-features/pull/727#discussion_r1537635491))

#### sets

Prefer this over multisyllabic alternatives, such as "defines", "determines", or "specifies".
Use "The property sets…" but never "The property defines…."
([#727](https://github.com/web-platform-dx/web-features/pull/727#discussion_r1537635491))

#### specifies

Avoid.
See [sets](#sets).
([#727](https://github.com/web-platform-dx/web-features/pull/727#discussion_r1537635491))

#### styling … as … by default

Use this phrase (or using another appropriate preposition, such as "styling in") to note conventional or standardized default styling.
The ellipses stand in for the thing being styled (e.g., "text") and the style itself (e.g., "italic").
Use it before [_also known as_ text](#also-known-as).
For example:

 > The `<small>` element represents side-comments and small print, like copyright and legal text, styling text in a reduced font size by default.
 
 ([#1403](https://github.com/web-platform-dx/web-features/pull/1403), [#1379](https://github.com/web-platform-dx/web-features/pull/1379))

#### usage

Never use "usage" in the sense of "using."
For example, instead of "The `input()` method enables the usage of…" write "The `input()` method uses…."
([#753](https://github.com/web-platform-dx/web-features/pull/753#discussion_r1560914869))

It's OK to use "usage" only in the sense of "consumption" (as in "mobile data usage") or "customary practice" (as in "the style guide's usage recommendations").

#### `window`

Because `window` is both the global object and represents the browser window, there are cases where it makes sense to refer to either `window.<name>` or `<name>` (such as `window.fetch()` or `fetch()`).
Use the most customary reference in each case.
If you're not sure what's customary, look to high-profile published examples, such as those on MDN reference pages for the feature.
([#913](https://github.com/web-platform-dx/web-features/pull/913#discussion_r1572601975))

## `caniuse` values

The `caniuse` key references one or more [Can I Use](https://caniuse.com/) feature IDs.
This is the part of a Can I Use URL after `https://caniuse.com/`.
For example, the Can I Use feature ID for [Flexbox](https://caniuse.com/flexbox) is `flexbox`.
For a complete list of IDs, run `npx tsx ./scripts/caniuse.ts`.

Setting a `caniuse` value says that a feature is approximately equivalent to or a superset of a Can I Use feature.
If you set a `caniuse` value, then the Can I Use site shows a status badge based on the feature's top-level headline `status` information.

Follow these guidelines when setting a `caniuse` value:

- Do not set a `caniuse` value if the Can I Use feature is merely related to the feature.
  For example, in [`grid.yml`](../features/grid.yml), do not set `caniuse: css-subgrid`.

- Do not set a `caniuse` value if the top-level headline `status` does not match Can I Use on whether each browser supports or does not support the feature.

  For example, if Can I Use shows that one browser of the core browser set does not support a feature but web-features's status reports that the feature is supported across all of the browsers, then do one of these:

  - Do not set the `caniuse` value for that feature.
  - Submit a correction to Can I Use.
  - Submit a correction to mdn/browser-compat-data.

- Do not set a `caniuse` value if the top-level headline `status` would not accurately reflect when a feature was last introduced to core browser set (the [keystone release](./baseline.md#interoperable-low-status) version number).

  For example, if Can I Use shows that Edge 79 introduced a feature, then the headline status must also show that Edge 79 introduced the feature.

- Do use `compute_from` to improve the correspondence of a feature's top-level headline status with Can I Use data.
  Use this in cases where later additions, such as the introduction of a minor property or method, brings the statuses out of alignment.

  But don't forget to use your judgement!
  Can I Use isn't perfect.
  Don't use `compute_from` in a way that would not make sense if the corresponding `caniuse` value didn't exist (for example, by pinning support before the introduction of an essential component of the feature).
  In such situations, it's better to comment out the `caniuse` value, make a `TODO` comment, and open an issue about why you did it.

If you see a discrepancy between Can I Use and a computed status that is less than one year for releases before 2020, please make a note of it in [#1499](https://github.com/web-platform-dx/web-features/issues/1499).

See also: [#1880](https://github.com/web-platform-dx/web-features/issues/1880).

## Groups

The `group` field references one or more groups.
You can find group definitions in the [`groups/`](../groups/) directory.

Groups are experimental.
It might not be clear how to group features until more features have been defined.

Don't assign features to two or more groups such that one group is an ancestor of another.
For example, don't assign a feature to both `css` and `fonts`, since `css` is the parent of `fonts`.

Do assign features to groups when there's an opportunity for future feature composition (see [#971](https://github.com/web-platform-dx/web-features/issues/971)).
For example, several features for the JavaScript `Array` interface are members of the `array` group.

## Discouraged

Rarely, the developers should not use a platform feature because it's the consensus of relevant stakeholders (i.e., a standards body and implementers), even if that feature is still implemented in browsers.
Mark a feature as discouraged when:

- The specification adopts clear language directing developers to stop using that feature or to prefer to an alternative.
  This is often through terms like "deprecated", "obsolete", or "legacy."
  They can also be in the form of one-off recommendations to use alternatives (such as "[…ought to be used instead](https://dom.spec.whatwg.org/#ref-for-concept-event%E2%91%A4%E2%91%A3)").

- The specification removes that feature from the specification without a succession plan (such as moving it to another specification).

- The specification editors intend to discourage or remove the feature from the specification.
  For example, meeting minutes show that a committee achieved consensus to remove a feature from a specification, even if the removal is not complete.

- All of the (present) implementers issue warnings when using that feature or have published something expressing an intention to unship that feature.


Do not mark a feature as discouraged when:

- The feature is merely old or unpopular, no matter how many [_considered harmful_](https://en.wikipedia.org/wiki/Considered_harmful) blog posts it may have garnered.
  For example, despite the existence of `fetch`, `XMLHttpRequest` is not a discouraged feature.

- The feature is controversial.
  Opposition to a feature (without consensus) is not sufficient to mark a feature as discouraged.
  For example, do not mark a feature as discouraged because a vendor has given it a negative standards position.

- The feature is buggy or not implemented in one or more browsers.
  Contribute to accurate support data instead.

When you set a `discouraged` block in a feature file, do:

- Set a (required) `according_to` URL, linking to evidence that the feature is discouraged.
  If possible, use the single most broadly applicable reference, such as specification text.
  If a feature is removed from a specification, link to an issue, pull request, or commit showing the removal.

- Set one or more (optional) `alternative` feature IDs that are whole or partial substitutes for the discouraged feature.
  An alternative doesn't have to be a narrow drop-in replacement for the discouraged feature but it must handle some use case of the discouraged feature.
  Guide developers to the most relevant features that would help them stop using the discouraged feature.
