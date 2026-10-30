# Compact Language Detector 2

The function `detect_language()` is vectorised and guesses the the
language of each string in `text` or returns `NA` if the language could
not reliably be determined. The function `detect_language_multi()` is
not vectorised and analyses the entire character vector as a whole. The
output includes the top 3 detected languages including the relative
proportion and the total number of text bytes that was reliably
classified.

## Usage

``` r
detect_language(text, plain_text = TRUE, lang_code = TRUE)

detect_language_mixed(text, plain_text = TRUE)
```

## Arguments

- text:

  a string with text to classify or a connection to read from

- plain_text:

  if `FALSE` then code skips HTML tags and expands HTML entities

- lang_code:

  return a language code instead of name

## Examples

``` r
# Vectorized function
text <- c("To be or not to be?", "Ce n'est pas grave.", "Nou breekt mijn klomp!")
detect_language(text)
#> [1] "en" "fr" "nl"

if (FALSE) { # \dontrun{
# Read HTML from connection
detect_language(url('http://www.un.org/ar/universal-declaration-human-rights/'), plain_text = FALSE)

# More detailed classification output
detect_language_mixed(
  url('http://www.un.org/fr/universal-declaration-human-rights/'), plain_text = FALSE)

detect_language_mixed(
  url('http://www.un.org/zh/universal-declaration-human-rights/'), plain_text = FALSE)
} # }
```
