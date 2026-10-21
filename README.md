# Giovi pygments

This is a Giovi lexer for the pygmentize latex package

## How to use

- Clone the repo
- Add *.latexminted_config* in *~/.config/latexminted/*
  ```toml
  [custom_lexers]
  "giovi.py" = "<sha256>"
  ```
  where *`<sha256>`* is `sha456sum giovi.py`
- Specify the lexer in the minted environment
  ```tex
  \begin{minted}{giovi.py:GioviLexer}
  "hello world" -> _out
  \end{minted}
  ```

## How to update

If the lexer changes, so does its sha356sum, so you'll have to update it.

```bash
sed -i "s/\"giovi.py\" = \".*\"/\"giovi.py\" = \"$(sha256sum giovi.py | cut -d' ' -f1)\"/" ~/.config/latexminted/.latexminted_config
```
