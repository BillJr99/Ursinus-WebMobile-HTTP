---
transition: zoom
---

## Base64 Encoding

- [Base64 Encoding](https://en.wikipedia.org/wiki/Base64) represents binary sequences as characters

```javascript
var data = "This is a test";
var encoded = btoa(data);
var decoded = atob(encoded); // === data
```