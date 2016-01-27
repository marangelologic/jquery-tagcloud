# Usage #

Call it on a jQuery object created from one element and pass an array of
objects with "tag" and "count" attributes. E.g.:

```
var tags = [{tag: "computers", count: 56}, {tag: "mobile" , count :12}, ... ];
$("#tagcloud").tagCloud(tags);
```

> The size of the tag in the cloud will be determined by the count values: tags with larger count values will be displayed larger. The count values are normalized so you can use any number. The tag with smallest (minimal, to be exact :)) count value will be displayed using '1em' size, the largest size is configurable. Currently a linear range is used, maybe later an exponential one will be developed.

# Configuration #

Optionally you can pass a configuration object to tagCloud as the second
parameter. Allowed settings are:

sort: Comparator function used for sort the tags before displaying, or false if no sorting needed.

> default: sort by tag text using
> > function (a, b) {return a.tag < b.tag ? -1 : (a.tag == b.tag ? 0 : 1)

click: Event handler which receives the tag name as first parameter and the original click event as second. The preventDefault() is called on event before passing so don't bother.


> default: does nothing:
> > function(tag, event) {}


maxFontSizeEm: Size of the largest tag in the cloud in css 'em'. The smallest one's size is 1em so this value is the ratio of the smallest and largest sizes.


> default: 4


# Styling #

> The plugin adds the "tagcloudlink" class to the generated tag links. Note that an "&nbsp;" is generated between the links too.