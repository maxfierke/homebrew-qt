# homebrew-qt
`brew install qt@5.7 --with-qtwebkit` as bottle

## Why?

There are some tools, e.g. 'capybara-webkit', that require you to have Qt5 with QtWebKit. Unfortunately, Homebrew does not ship a compiled bottle for Qt with QtWebKit.
To install all the required dependencies on macOS, you would have to run `brew install qt@5.7 --with-qtwebkit` and wait several hours for the whole Qt suite to compile from scratch with QtWebKit.

## How to use it?

    brew uninstall qt5 qt qt@5.5 qt@5.7
    brew install maxfierke/qt/qt57-webkit

And you're good to go. This will install a pre-compiled bottle (currently only on High Sierra).

## Troubleshooting

### It can't find `cmake`

`cmake` is not linked automatically to `/usr/local/bin/`. Run `brew info qt57-webkit` to check out the caveats. If it suits your environment, you may just run `brew link --force qt57-webkit`, though this is not recommended if you're using Qt or qmake to build things outside of Homebrew.

## Updating the bottle

Clone this repository and run `./update.sh`.
It will tell you what to do.
