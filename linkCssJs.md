## linkCssJs()

### Description
```
Builds <link> and <script> tags with resources and attaches to the DOM
```

### Dependencies
```
jQuery preloader
```

### Module
```
function linkCssJs(filename) {

  var obj = {
    getStylesheet: function() {
			var css = document.createElement('link');
			css.rel = 'stylesheet';
			css.async = false;
			css.href = 'css/' + filename + '.css';
			(document.getElementsByTagName('head')[0]).appendChild(css);
    },
    getScript: function() {
			var js = document.createElement('script');
			js.type = 'text/javascript';
			js.async = false;
			js.src = 'scripts/' + filename + '.js';
			(document.getElementsByTagName('head')[0]).appendChild(js);
    }
  }
  return obj;
}
```
### Usage
**linkCssJs()** assumes the style and script files share the same filename.
```
<head>
	<script>
		resources = linkCssJs('page23');
		resources.getStylesheet();
		resources.getScript();
	</script>
</head>
```

