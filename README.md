## Homebrew Terminology

| Term           | Description                                                | Example                                              |
|----------------|------------------------------------------------------------|------------------------------------------------------|
| **Formula**    | The package definition                                     | `ls /usr/local/Library/Formula (grep to search)`     |
| **Keg**        | The installation prefix of a **Formula**                   | `ls /usr/local/Cellar          (or  brew ls)`        |
| **opt prefix** | A symlink to the active version of a **Keg**               | `ls /usr/local/opt/foo`                              |
| **Cellar**     | All **Kegs** are installed here                            | `ls /usr/local/Cellar`                               |
| **Tap**        | An optional Git repository of **Formulae** and/or commands | `/usr/local/Library/Taps/homebrew/homebrew-versions` |
| **Bottle**     | Pre-built **Keg** used instead of building from source     | `qt-4.8.4.mavericks.bottle.tar.gz`                   |
