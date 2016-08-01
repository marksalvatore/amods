## adjacentPage()

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
function adjacentPage(filename) {
  var obj = {
    getPage: function() {
      console.log("adjacentPage()");
      $('#preloader').fadeIn('fast', function() {
        loadPage(filename);
      })
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
// create the objects for the specific page
nextPage = adjacentPage(pages.a1_03 + '.html');
prevPage = adjacentPage(pages.a1_01 + '.html');

// reference the object's getPage() method globally
addNext = function() {
	$("#nextButton").unbind("click");
	$("#nextButton").click(function(){
		nextPage.getPage();
	});
	$("#nextButton").removeClass("grayscale");
};

addPrev = function() {
	$("#prevButton").unbind("click");
	$("#prevButton").click(function(){
		prevPage.getPage();
	});
	$("#prevButton").removeClass("grayscale");
};
```

