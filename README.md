# team-h

```javascript

$w.onReady(function () {
	fetch('https://api.github.com/search/users?q=tom+repos')
	.then(response => response.json())
	.then(({items}) => {
		console.log(items.map((item) => item.login))
	})
});
```
