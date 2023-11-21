# Minimal Example Qrto crash with multibib

To reproduce:

- Quarto version: 1.3.450
- Add multibib extension: `quarto add pandoc-ext/mulibi`
- Build project: `quarto render`

Process will show an error like this:

```
ERROR: TypeError: bibliography.map is not a function

TypeError: bibliography.map is not a function
    at bookBibliography (file:///Applications/quarto/bin/quarto.js:98657:48)
    at async bookBibliographyPostRender (file:///Applications/quarto/bin/quarto.js:98689:55)
    at async Object.bookPostRender [as postRender] (file:///Applications/quarto/bin/quarto.js:99065:9)
    at async renderProject (file:///Applications/quarto/bin/quarto.js:86998:13)
    at async Command.fn (file:///Applications/quarto/bin/quarto.js:90856:32)
    at async Command.execute (file:///Applications/quarto/bin/quarto.js:8437:13)
    at async quarto (file:///Applications/quarto/bin/quarto.js:127545:5)
    at async file:///Applications/quarto/bin/quarto.js:127563:9
```

Removing the Quarto `book` project type from the `.yaml` resolves this issue.
