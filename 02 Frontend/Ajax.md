
**Q: A quoi sert Ajax** #D1 



# Hello Ajax

```Javascript
var xhr = new XMLHttpRequest();
xhr.open('GET', 'http://localhost:8080/ajax-demo/ajax-servlet');
xhr.setRequestHeader('abc', 'cba');
xhr.send('a=100&b=200');

xhr.onreadystatechange = function(){
    if (xhr.readyState === 4) {
        if (xhr.status >= 200 && xhr.readyState < 300) {
            console.log(xhr);
			consold.log(this);
			alert(this.responseTest)
        } else {
            
        }
    }
}
```