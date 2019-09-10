"#sran8680"

Bonus question:

The verification was done by the Cookies.js files' get function:

```get: function(b, c) {
		for (var a = [], e = document.cookie.split(/; */), d = 0; d < e.length; d++) {
			var f = e[d].split('=');
			f[0] == encodeURIComponent(b) && a.push(decodeURIComponent(f[1].replace(/\+/g, '%20')));
		}
		return c ? a : a[0];
	}
```

You run through a for loop which iterates as many times as the cookie split array (variable e) has elements. Within the for loop is where the actual encoding occurs and then returns a[0] unless a c parameter was given in which case a is returned.

To reverse the string you simply return an array of all the elements of a reversed (in our case we only returned a[0]).

```get: function(b, c) {
		for (var a = [], e = document.cookie.split(/; */), d = 0; d < e.length; d++) {
			var f = e[d].split('=');
			f[0] == encodeURIComponent(b) && a.push(decodeURIComponent(f[1].replace(/\+/g, '%20')));
		}
        for (int i = 0; i < a.length; i++) {
            a[i] = a[i].split("").reverse().join("");
        }
		return c ? a : a[0];
	}
```

Here we simply split the strings in the a array into an array, reverse the array and then rejoin it. Both a and a[0] will return the reversed values of what we want. :)
