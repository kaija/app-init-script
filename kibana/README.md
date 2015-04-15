1. Copy kibana source code to /usr/share/kibana

2. Add patch to kibana main program
/usr/share/kibana/src/app.js


```javascript
var proxy = require('./routes/proxy');
var fs = require('fs');

console.log("Kibana pid is " + process.pid);
fs.writeFileSync('/var/run/kibana.pid', process.pid.toString());
```


3. Run

sudo /etc/init.d/kibana start | stop
