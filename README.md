# team-h

### Back-end code

### back-end part

```javascript

import {fetch} from 'wix-fetch';

/*
https://developer.github.com/v3/users/#get-all-users
this API search for all users in github that match your query 
*/
export function getUsers(parameter) {
	const url = 'https://api.github.com/search/users?q=' + parameter;
	return fetch(url, {
		method: 'get'
	})
	.then(response => response.json())
}
/*
https://developer.github.com/v3/search/#search-topics

*/
export function getTopics(parameter) {
	const url = 'https://api.github.com/search/topics?q=' + parameter;
	return fetch(url, {
		method: 'get', 
		headers: {
            'Content-Type': 'application/vnd.github.mercy-preview+json'
        }
	})
	.then(response => response.json())
}

/*
https://developer.github.com/v3/projects/#create-a-user-project
this API create a project, then I should be able to invite the user.
*/
export function createProject(data) {
	const url = 'https://api.github.com/user/projects';
	console.log('url' + url);
	return fetch(url, {
		method: 'post', 
		body: JSON.stringify(data)
	})
	.then(response => response.json())
}
```

## Front-end part

```javascript
// For full API documentation, including code examples, visit http://wix.to/94BuAAs
import {getUsers, test} from 'backend/aModule';

$w.onReady(function () {
	/* */
});

export function button3_click(event, $w) {
	//Add your code for this event here: 

	getUsers($w('#projectInput').value)
	.then(users => {
		var result = '';
		users.items.slice(1, 20).forEach(function(item) {
  			console.log(item);
			result += "Name: " + item.login + " Score: " + item.score + '\n'
		});
		$w('#result').text = result;
		
	})
	
}
```
```

### Front-end code

```javascript
// For full API documentation, including code examples, visit http://wix.to/94BuAAs
import {getUsers, test} from 'backend/aModule';

$w.onReady(function () {
	/* */
});

export function button3_click(event, $w) {
	//Add your code for this event here: 

	getUsers($w('#projectInput').value)
	.then(users => {
		var result = '';
		users.items.slice(1, 20).forEach(function(item) {
  			console.log(item);
			result += "Name: " + item.login + " Score: " + item.score + '\n'
		});
		$w('#result').text = result;
		
	})
	
}
```
