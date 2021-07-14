# Echo-Node
NodeJS library for Echo (https://echo.ac/)

## Install using:
`npm i echo-tool-api`

## Example:
```javascript
const Echo = new require('echo-tool-api');

var echoUser = new Echo.API("key");

echoUser.on("236517", "started", () => {
    console.log("started!");
}); //spams with started after started, so might wanna only run shit once

echoUser.on("236517", "finished", () => {
    console.log("finitoed!");
});

echoUser.on("236517", "progress_change", (percent) => {
    console.log(percent + "%");
});

echoUser.listen("236517");

echoUser.getUserInfo().then(function(info) {
    console.log(info);
}); //also theres getScans(length, extended, enterprise), getPlayerInfo(player), and refreshPin(), getPinInfo() for enterprises
```
