When handling form submission with javascrit (e.g) we have access to the event object.

Using that event prevent default method to stop form submission

```javascript
function handleSubmission(event) {
	event.preventDefault();
}
```

Returning `false` will not work. Some browser, like Chrome, won't work with this techinique.

Might be helpful to also return back if your form will submit the action to another route/page.

For example:

```html
<form action="/users/create" action="post">
	
</form>
```

```javascript
function handleSubmission(event) {
	event.preventDefault();
	window.history.back();
}
```