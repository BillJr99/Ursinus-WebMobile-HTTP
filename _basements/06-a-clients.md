---
slide: 06-clients
---

## HTTP Clients

```javascript
const https = require('https');

https.get('https://api.weatherusa.net/v1/obs?station_id=KLOM', (resp) => {
  let data = '';

  resp.on('data', (chunk) => {
    data += chunk;
  });

  resp.on('end', () => {
    const respobj = JSON.parse(data);

    console.log(data);
    console.log("Weather at " + respobj[0].station_id);
    console.log("Sky: " + respobj[0].sky);
    console.log("Temperature: " + respobj[0].t_f);
    
    var sunset = new Date(0);
    sunset.setUTCSeconds(respobj[0].sunset_t);
    console.log("Sunset time: " + sunset);
  });
}).on('error', (e) => {
  console.log(e.message);
});
```

- Save as `httpclient.js` and run with: `node httpclient.js`