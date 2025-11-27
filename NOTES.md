# WebType Project Notes

## Step 1: Adding Google Fonts - Montserrat

### What Was Added

Three lines were added to the `<head>` section of `index.html` (lines 7-9):

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&display=swap" rel="stylesheet">
```

### What Each Line Does

1. **Line 7: `<link rel="preconnect" href="https://fonts.googleapis.com">`**
   - Establishes an early connection to Google's font server
   - Reduces latency when the actual font request is made
   - Performance optimization

2. **Line 8: `<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>`**
   - Establishes an early connection to Google's static content server (where font files are hosted)
   - `crossorigin` attribute is required because font files are loaded from a different domain
   - Performance optimization

3. **Line 9: The actual font import**
   - `family=Montserrat` - Specifies which font family to load
   - `ital,wght@0,100..900;1,100..900` - Loads the variable font with all weights
     - `0,100..900` = non-italic, weights 100-900
     - `1,100..900` = italic, weights 100-900
   - `display=swap` - Shows fallback font first, then swaps to Montserrat when loaded (prevents invisible text)

### Options That Were Available

#### Loading Method Options:
1. **Standard `<link>` method** ✓ CHOSEN
   - Clean, in HTML `<head>`
   - Good performance
   - Recommended approach

2. **`@import` in CSS**
   - Not chosen: blocks rendering, slower performance

#### Font Weight Options:
1. **Specific weights only** (e.g., 400, 700)
   - Smaller file size
   - Limited flexibility
   - Example: `wght@400;700`

2. **Variable font with all weights** ✓ CHOSEN
   - Access to all weights 100-900
   - Smooth transitions between weights
   - Better for typography experimentation
   - Example: `wght@100..900`

#### Italic Options:
1. **No italics**
   - Smaller file size
   - Example: `wght@100..900`

2. **Include italics** ✓ CHOSEN
   - Both upright and italic styles available
   - More complete typography toolkit
   - Example: `ital,wght@0,100..900;1,100..900`

### Choices Made

- **Variable font**: Full weight range (100-900) for maximum flexibility in typography experiments
- **Italics included**: Both upright and italic variants
- **Standard link method**: Using `<link>` tags in HTML for optimal performance
- **Font display swap**: Ensures text is visible while font loads

### Next Steps

To use Montserrat in CSS:
```css
body {
    font-family: 'Montserrat', sans-serif;
}
```

For specific weights:
```css
h1 {
    font-family: 'Montserrat', sans-serif;
    font-weight: 700; /* or any value from 100-900 */
}
```

For italic:
```css
em {
    font-family: 'Montserrat', sans-serif;
    font-style: italic;
}
```
