While using express, there might come a situation where you can choose to use `res.redirect` or `res.location`.

They are pretty much the same except that one does a bit more work then the other.

`res.location` just sets the response header. It will not set a status code or close the response. By not closing the response, you'll need to call `res.end()` on your own.

`res.redirect`, by default will set the status to `302` but you can change the status like this

```javascript
res.redirect(301, '/path/to/redirect')
```

Will send a response body informing about the redirect.


[**SO source (original answer)**](https://stackoverflow.com/a/22678011)