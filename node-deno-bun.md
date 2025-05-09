### Run a js code with module declaration for node, deno & bun

* app.js

```js
  // app.js (or any other file where you want to use getDateTime)
import { getDateTime } from './GetDateTime.js';  // Make sure the path is correct

const { formattedTime, day, date } = getDateTime();
console.log(`Time: ${formattedTime}`);
console.log(`Day: ${day}`);
console.log(`Date: ${date}`);
```

* GetDateTime.js

```js
export const getDateTime = () => {
    const now = new Date();
    const hour = now.getHours();
    const minute = now.getMinutes();
    const second = now.getSeconds();

    const amPm = hour >= 12 ? "PM" : "AM";
    const formattedHour = hour % 12 || 12;
    const formattedTime = `${formattedHour}:${String(minute).padStart(2, "0")}:${String(second).padStart(2, "0")} ${amPm}`;

    const days = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday"];
    const months = ["January", "February", "March", "April", "May", "June",
        "July", "August", "September", "October", "November", "December"];

    const day = days[now.getDay()];
    const date = `${months[now.getMonth()]} ${now.getDate()}, ${now.getFullYear()}`;

    return {formattedTime, day, date};
}
```
