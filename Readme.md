## Q5 — HTML corrections

File: q5.html
Image used: test.jpeg
Validator: https://validator.w3.org/ (result: 0 errors after corrections)

### Actual HTML5 validity errors

1. `</html>` appeared before `<body>`. The closing `</html>` tag ends the document, so everything else must be inside it. I moved it to the very end.

2. Stray closing `</body>` and `</html>` tags were duplicated three extra times at the end with no matching opening tags. Removed.

3. `<img src=test.jpeg with=300 height=auto>` had two invalid attributes. `with` should be `width`, and `auto` is not a valid value for the HTML `height` attribute (height in HTML must be a number, or omitted and handled by CSS). I corrected the attribute name and removed the invalid height, letting the browser scale proportionally.

4. `<abbr name="lobortis">` used the wrong attribute. `<abbr>` takes `title`, not `name`. Corrected.

5. `<code><b>...</code></b>` had mismatched closing tags. The `<b>` opened inside `<code>`, so it must close inside too. Corrected to `<code><b>...</b></code>`.

6. `<a href=https://www.bigcabal.com>` had an unquoted URL containing `://` and `=`. Unquoted attribute values cannot contain those characters. Corrected with quotes.

7. The original had no `<!DOCTYPE html>`. Added the HTML5 doctype at the top.

### Accessibility and style improvements

- Missing `lang` attribute on `<html>`. Added `lang="en"`.
- Image had no `alt` attribute. Added a descriptive one.
- `<button>` had no `type`. Added `type="button"` to prevent unintended form submission behaviour.
- Content was not wrapped in a semantic landmark. Added `<main>` around the page content.

### Five HTML-only improvements for search and interpretation

1. **`<html lang="en">`** — tells browsers and assistive technology what language the page is in. Screen readers use it for correct pronunciation and search engines use it for language targeting.

2. **`<meta charset="UTF-8">`** — declares the character encoding so the browser renders text correctly without guessing.

3. **`<meta name="description" content="...">`** — the description search engines may show under the page title in results. It does not affect ranking directly but affects click-through rate.

4. **`alt` attribute on the image** — provides a text description for search engines and for users who cannot see the image. Also displayed if the image fails to load.

5. **Descriptive `<title>`** — the title is the primary signal in search results and in the browser tab. The original "Example" gave no context. The new title describes the page.

### Validation

Ran the corrected file through https://validator.w3.org/. Result: 0 errors, 0 warnings.
