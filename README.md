# slugify

A minimal slugification library in zepto. It is in alpha right now.

## Usage

There is only one routine, `slugify:slugify`.

Using it looks somewhat like this:
```clojure
(slugify:slugify "please slugify this text")
=> "please-slugify-this-text"
(slugify:slugify "ple'ase slügify this text" 
(make-hash ["separator" "_"]
           ["replace" slugify:replace:german]
           ["max-length" 15]
           ["unsafe" ("this")]
           ["unsafe-symbols"("'")]))
=> "please_sluegify"
```

This showcases all five configuration options, namely:
* **separator** (string): this customizes the string that separates words in the slug. (default: "-")
* **replace** (hash-map): this customizes the replacement behaviour for different alphabets.
                         Currently supported (i.e. in the package) are German and Japanese
                         (Hiragana & Katakana), both are select via `slugify:replace:all`,
                         which is also the default.
* **max-length** (int): this customizes the maximal length of the slug. All words following it
                       will be truncated. (default: 100)
* **unsafe** (list of strings): this customizes words that should be deleted. (default: [])
* **unsafe-symbols** (list of strings): this customizes fragments that should be deleted. (default: [])

<br/>

*Have fun!*
