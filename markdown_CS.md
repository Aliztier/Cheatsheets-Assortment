<!-- General Markdown -->

<!-- Headings -->
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6

<!-- Italics -->
*This text* is italic

_This text_ is italic

<!-- Strong -->
**This text** is italic

__This text__ is italic

<!-- Combined -->
**This _text_** uses both italics and strong.
<!-- Strikethrough -->
~~This text~~ is strikethrough

<!-- Horizontal Rule -->

---
___

<!-- Blockquote -->
> This is a quote

<!-- Links -->
[I'm an inline-style link](https://www.google.com)

[I'm an inline-style link with title](https://www.google.com "Google's Homepage")

[I'm a reference-style link][Arbitrary case-insensitive reference text]

[I'm a relative reference to a repository file](..blob/master/README.md)

[You can use numbers for reference-style link definitions][1]

URLs and URLs in angle brackets will automatically get turned into links. 
http://www.example.com or <http://www.example.com> and sometimes 
example.com (but not on Github, for example).

Or leave it empty and use the [link text itself].

[arbitrary case-insensitive reference text]: https://www.mozilla.org
[1]: http://youtube.com
[link text itself]: http://www.reddit.com

<!-- UL -->
* Item 1
* Item 2
* Item 3
  - Nested Item 1
  + Nested Item 2
  * Nested Item 3

<!-- OL -->
1. Item 1
1. Item 2
1. Item 3

<!-- Inline Code Block -->
Inline code has `back ticks` around it`<p>This is a paragraph</p>`

<!-- Images -->
![Markdown Logo](https://markdown-here.com/img/icon256.png)
 
![alt text][logo]

[logo]: https://markdown-here.com/img/icon256.png "Logo Title Text 2"

<!-- Github Markdown -->

<!-- Code Blocks -->
```bash
  npm install

  npm start
```

```javascript
  function add(num1, num2) {
    return num1 + num2;
  }
```

```python
  def add(num1, num2):
    return num1 + num2
```

<!-- Tables -->
| Name     | Email          |
| -------- | -------------- |
| John Doe | john@gmail.com |
| Jane Doe | jane@gmail.com |

There must be at least 3 dashes separating each header cell.
The outer pipes (|) are optional, and you don't need to make the 
raw Markdown line up prettily. You can also use inline Markdown.

 Markdown | Less | Pretty 
 --- | --- | --- 
*Still* | `renders` | **nicely**
 1 | 2 | 3 

<!-- Task List -->
* [x] Task 1
* [x] Task 2
* [ ] Task 3