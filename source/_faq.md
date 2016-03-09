# Frequently Asked Questions

## Using Java how do I get the JSON back on 400+ status returns?

[Workaround from bugs.java.com](http://bugs.java.com/bugdatabase/view_bug.do?bug_id=4513568)

> Example Java Code

```java
HttpURLConnection httpConn = (HttpURLConnection)_urlConnection;
InputStream _is;
if (httpConn.getResponseCode() == 200) {
    _is = httpConn.getInputStream();
} else {
     / error from server /
    _is = httpConn.getErrorStream();
}
```
