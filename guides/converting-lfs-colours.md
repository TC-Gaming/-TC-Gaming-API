# Converting LFS Colours

Live for Speed text that includes colours is encoded. This guide will help you to extract the colours from the text.

Imagine you made a call to the [User Profile API](../apis/citydriving-statistics-api/user-profile-api.md) and wanted to decode the following nickname: `"nickname": "^1[TC]\u00bbPete\u00ab",`. The UTF-8 encoding is not an issue because the browser decodes that automatically for us but the LFS colour prefixes eg. `^1`, will need to be decoded by us before being presented.

Our code examples are available in JavaScript and PHP _\(change language in the top right\)._

## Reference Implementations

The list of LFS colour codes is as follows:

| Colour | Code |
| :--- | :--- |
| Black | `^0` |
| Red | `^1` |
| Light Green | `^2` |
| Yellow | `^3` |
| Blue | `^4` |
| Purple | `^5` |
| Light Blue | `^6` |
| White | `^7` |
| Dark Green \(Default\) | `^8` |
| Original text colour and codepage | `^9` |

All of the examples in this guide require the following CSS to properly display the colours:

### CSS

```css
.lfs_col0 {color : #000000;}
.lfs_col1 {color : #ff0000;}
.lfs_col2 {color : #00ff00;}
.lfs_col3 {color : #ffff00;}
.lfs_col4 {color : #0000ff;}
.lfs_col5 {color : #ff00ff;}
.lfs_col6 {color : #00ffff;}
.lfs_col7 {color : #ffffff;}
.lfs_col8, .lfs_col9 {color : #8a8a8a;}
```

{% tabs %}
{% tab title="JavaScript" %}
### JavaScript

```javascript
function LFSColours(str) {
  var parts = str.split(/(\^\d)/g).slice(1);
  var res = "";
  parts.forEach(function(el, i, arr) {
    (i % 2 === 0) ? arr[i] = el.slice(1) : res += '<span class="lfs_col' + arr[i-1] + '">' + el + '</span>';
  });
  return res;
}
```

#### Example usage

**Try out this example on** [**JS Bin**](https://jsbin.com/sicaxov/edit?css,js,output)

```javascript
var str = '^1[TC]\u00bbPete\u00ab';

document.body.innerHTML = LFSColours(str);
```
{% endtab %}

{% tab title="PHP" %}
### PHP

```php
function LFSColours($raw) {
  if ($raw === null) return "";
  $parts = preg_split('/(?=\^\d)/', $raw);
  $res = "";
  foreach ($parts as $part) {
    if (preg_match('/(\^\d)(.*)/', $part, $m) === 1) {
      $res .= "<span class='lfs_col" . $m[1][1] . "'>" . htmlspecialchars($m[2]) . "</span>";
    }
    else $res .= "<span class='lfs_col8'>" . htmlspecialchars($part) . "</span>";
  }
  return $res;
}
```

#### Example usage

```php
$str = '^1[TC]\u00bbPete\u00ab';

echo(LFSColours($str));
```
{% endtab %}
{% endtabs %}

