# Glyph

> Over 100 glyph icons in a font that can be used for button, label and frame captions.

![Example](http://i.imgur.com/3Rs1WWZ.png)

## Usage

This mod is still in experimental phase. I don't recommend using it for production use yet, but feel free to experiment with it and leave feedback :)

The mod adds a glyph font contianing numerous vector icons, along with a locale dictionary allowing them to be referenced by name in your code.

### Setting the font

Set the font in a prototype style sheet (see `core` and `base` mods for examples of that) or, at runtime, via the [`.style.font`](http://lua-api.factorio.com/latest/LuaStyle.html) property of a [LuaGuiElement](http://lua-api.factorio.com/latest/LuaGuiElement.html), for example:

```lua
game.players[1].top.my_gui_element.style.font = 'glyph-large'
```

Four font sizes are currently provided:

* `glyph-small` - 12pt text
* `glyph` - 14pt text
* `glyph-medium` - 16pt text
* `glyph-large` - 18pt text

You can add additional sizes - see `prototypes/fonts.lua` for example.

### Choosing the glyph

After downloading the mod, unzip it and open the `reference.htm` in a browser to display a handy chart listing all the glyphs and their associated [locale keys](http://lua-api.factorio.com/latest/Concepts.html#LocalisedString).

To display a glyph, set `yourElement.caption` to the relevant key for the icon you want, for example:

```lua
game.players[1].top.my_gui_element.caption = { 'glyph-biter' }
```

## License

The .lua, .cfg and .json files were made by me (aubergine) and are MIT licensed.

The font was built using [Fontastic](http://fontastic.me/), a site that allows glyphs from numerous open source fonts (and a few commerical ones, which aren't used for obvious reasons) to be merged in to a single font file with custom character code mappings.

Glyphs are from the following fonts:

* [Ionicons2](https://github.com/driftyco/ionicons) - [MIT license](https://opensource.org/licenses/MIT)
* [Octicons](https://github.com/primer/octicons) - [SIL OFL 1.1](http://scripts.sil.org/cms/scripts/page.php?site_id=nrsi&id=OFL)

The reference.htm and associated .css were automatically created by Fontastic, and subsequently edited by me. As far as I can tell, those files are MIT licensed, although the Fontastic app doesn't specifically state that in the files themselves.

## Future plans

1. Move all glyphs to [private unicode space](https://en.wikipedia.org/wiki/Private_Use_Areas) (`U+E000`–`U+F8FF`)
2. Merge with vanilla fonts so that glyphs and normal text can be used together
3. Add more glyphs based on feedback (possibly remove some too)
