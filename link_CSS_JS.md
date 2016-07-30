## adjacentPage()

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
function link_CSS_JS(filename) {
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
### Setup
```
// map filenames to object
pages = new Object();
pages.a1_01 = 'intro_page01_Reveal01';
pages.a1_02 = 'intro_page02_Text01';
pages.a1_03 = 'intro_page03_Text02';
```

### Usage
```
<head>
	<script>
		resources = link_CSS_JS(pages.in_10);
		resources.getStylesheet();
		resources.getScript();
	</script>
</head>

```

