# Console Utilities

The Console Utilities API contains a collection of convenience functions for performing common tasks: selecting and inspecting DOM elements, displaying data in readable format, monitoring DOM events, and more.

> **Warning: **These functions only work when you call them from the Chrome DevTools Console. They won't work if you try to call them in your scripts.

#### $\_

`$_`returns the value of the most recently evaluated expression.

![](/console/recently-evaluated-expression.png)

### $0 - $4

The`$0`,`$1`,`$2`,`$3`and`$4`commands work as a historical reference to the last five DOM elements inspected within the Elements panel or the last five JavaScript heap objects selected in the Profiles panel.

`$0`returns the most recently selected element or JavaScript object,`$1`returns the second most recently selected one, and so on.

![](/elements/recent-inspected.png)

### $\(selector, \[startNode\]\)

`$(selector)`returns the reference to the first DOM element with the specified CSS selector. This function is an alias for the [document.querySelector\(\)](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector) function.

![](/console/selector-img.png)

### $$\(selector, \[startNode\]\)

`$$(selector)`returns an array of elements that match the given CSS selector. This command is equivalent to calling [document.querySelectorAll\(\)](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll).

### copy\(object\)

`copy(object)`copies a string representation of the specified object to the clipboard.

### dir\(object\)

`dir(object)`displays an object-style listing of all the specified object's properties. This method is an alias for the Console API's`console.dir()`method.

### inspect\(object/function\)

`inspect(object/function)`opens and selects the specified element or object in the appropriate panel: either the Elements panel for DOM elements or the Profiles panel for JavaScript heap objects.

The following example opens the`document.body`in the Elements panel:

```js
inspect(document.body);
```

### getEventListeners\(object\)

`getEventListeners(object)`returns the event listeners registered on the specified object. The return value is an object that contains an array for each registered event type \(`click`or`keydown` , for example\).

### keys\(object\)

`keys(object)`returns an array containing the names of the properties belonging to the specified object. To get the associated values of the same properties, use`values()`.![](/console/keys-values.png)

### monitor\(function\)

When the function specified is called, a message is logged to the console that indicates the function name along with the arguments that are passed to the function when it was called.

![](/console/monitor.png)  
Use`unmonitor(function)`to cease monitoring.



### monitorEvents\(object\[, events\]\)

When one of the specified events occurs on the specified object, the Event object is logged to the console. You can specify a single event to monitor, an array of events, or one of the generic events "types" mapped to a predefined collection of events.

![](/console/monitor-events %281%29.png)The following defines an array to monitor both "resize" and "scroll" events on the window object:

```js
monitorEvents(window, ["resize","scroll"])
```

`unmonitorEvents(object[, events])`stops monitoring events for the specified object and events.  
  


### table\(data\[, columns\]\)

Log object data with table formatting by passing in a data object in with optional column headings. For example, to display a list of names using a table in the console.

![](/console/table.png)





