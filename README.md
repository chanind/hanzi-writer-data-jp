# Hanzi Writer Japanese Data

## About

This is the character data used by [Hanzi Writer](https://github.com/chanind/hanzi-writer) for Japanese.
**NOTE: This is currently experimental**

- This data is licensed separately from the Hanzi Writer source code.
- This allows users who wish to import character data in NPM to do so without forcing everyone to download the character data along with Hanzi Writer.
- Publishing on NPM makes this data available on the [jsdelivr CDN](https://www.jsdelivr.com/package/npm/hanzi-writer-data-jp), so data can be loaded via, for instance, https://cdn.jsdelivr.net/npm/hanzi-writer-data-jp@latest/私.json. 

Check out [chanind.github.io/hanzi-writer](https://chanind.github.io/hanzi-writer) for more info about Hanzi Writer.

## Usage
Until this is supported directly in Hanzi Writer, you'll need to use a custom `charDataLoader` function to use this data in Hanzi Writer. An example of how you can do that using `fetch` and the content on jsDelivr is shown below:

```
HanziWriter.create('target-div', '私', {
  width: 400,
	height: 400,
  charDataLoader: (char, onLoad, onError) => {
    fetch(`https://cdn.jsdelivr.net/npm/hanzi-writer-data-jp@0/${char}.json`)
      .then(res => res.json())
      .then(onLoad)
      .catch(onError);
  }
})
```

## License

This data comes from [animCJK](https://github.com/parsimonhi/animCJK) and the [Make Me A Hanzi](https://github.com/skishore/makemeahanzi) project, which extracted the data from fonts by [Arphic Technology](http://www.arphic.com/), a Taiwanese font forge that released their work under a permissive license in 1999. You can redistribute and/or modify this data under the terms of the Arphic Public License as published by Arphic Technology Co., Ltd. A copy of this license can be found in [ARPHICPL.TXT](https://raw.githubusercontent.com/chanind/hanzi-writer-data/master/ARPHICPL.TXT).

AnimCJK's data is licensed under LGPL.
You can redistribute and/or modify these files under the terms of the GNU
Lesser General Public License as published by the Free Software Foundation,
either version 3 of the license, or (at your option) any later version. You
should have received a copy of this license (the file "LGPL.txt") along with
these files; if not, see <http://www.gnu.org/licenses/>.
