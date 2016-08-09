## nextPage()

### Description
```
Front/Back paging feature
```

### Dependencies
```
jQuery
```

### Module
```
function goNextPage() {
  var obj = {
    getPage: function() {
      console.log('goNextPage()');
      $('#preloader').fadeIn('fast', function() {
      	nav.currPage++;
        loadPage(nav.pages[nav.currPage] + '.html');
      })
    }
  }
  return obj;
}

function goPrevPage() {
  var obj = {
    getPage: function() {
      console.log('goPrevPage()');
      $('#preloader').fadeIn('fast', function() {
      	nav.currPage--;
        loadPage(nav.pages[nav.currPage] + '.html');
      })
    }
  }
  return obj;
}

```
### Setup
```
// map filenames to object
nav = {
	"currPage" : 0,
	"pages" : [
		'intro_page01_Reveal01',
		'intro_page02_Text01',
		'intro_page03_Text02',
		'intro_page04_Text03',
		...
		]
```

### Usage
```
// Set  vars in the js for your page:

	nextPage = goNextPage();
	prevPage = goPrevPage();

// Reference your var's getPage() method:

	nextPage.getPage();
```

