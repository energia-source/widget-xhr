# Documentation widget-xkr

Widget Javascript XHR is a library used to make a GET/POST request.

## Usage

So the basic setup looks something like this for perform parallel delete actions:

```

let requests = [],
    choosed = [1, 2, 3, '<moore id>'];

for (let x in choosed) {
    let xhr = new WXmlHttpRequest(),
        url = '/api/sso/oauth/delete'
            + String.fromCharCode(47)
            + encodeURIComponent(choosed[x])
            + String.fromCharCode(63)
            + 'timestamp'
            + String.fromCharCode(61)
            + Date.now();

    requests.push(xhr);

    xhr.setRequestUrl(url);
    xhr.setCallbackSuccess(function () {
        let parser = document.createElement('a');
        parser.href = this.getXHR().responseURL;

        let split = parser.pathname.split('/'),
        key = split[split.length - 1] === 'delete'
            ? null
            : split[split.length - 1];

         // widgets.infinite.getBody().removeTR(key);
        choosed = choosed.filter(function (element) {
            return element != key;
        });
    });
}

for (let item = 0; item < requests.length; item++)
    requests[item].request();

delete requests;

```

## Structure

library:
    - [window.WXmlHttpRequest](https://github.com/energia-source/widget-xkr#class-wxmlhttprequest-usable-methods)

<br>

#### ***Class window.WXmlHttpRequest usable methods***

##### `constructor()`

The constructor function creates an object that has a property called xhr. The xhr property is an object that has a property called construct. The construct property is an object that has a property called addEventListener. The addEventListener property is a function that has a parameter called event. The event parameter is an object that has a property called target. The target property is an object that has a property called responseText. The responseText property is a string that has a value of null.

The constructor function also creates an object that has a property called xhr. The xhr property is an object that has a property called construct. The construct property is an object that has a property called addEventListener. The addEventListener property is a function that has a parameter called event. The event parameter is an object that has a property called target.

##### `setHardcode(key, value)`

Set a hardcoded value for a key

 * **Parameters:**
   * `key` — The name of the parameter.
   * `value` — The value to set.
 * **Returns:** The object itself.

##### `getHardcode()`

It returns the hardcode value.

 * **Returns:** The hardcode property of the XHR object.

##### `deleteHardcode(key)`

Delete a hardcoded value from the hardcoded object

 * **Parameters:** `key` — The key to delete.
 * **Returns:** The object itself.

##### `setCallbackSuccess(func)`

Set the success callback for the XHR object

 * **Parameters:** `func` — The function to be called when the request is successful.
 * **Returns:** The `ajax` function is being returned.

##### `getCallbackSuccess()`

Get the callback function for the success event

 * **Returns:** The success callback function.

##### `setCallbackFail(func)`

Set the callback function for the XHR request

 * **Parameters:** `func` — The function to call when the request is complete.
 * **Returns:** The XHR object.

##### `getCallbackFail()`

It returns the callback function for the fail event.

 * **Returns:** The callback function for the fail event.

##### `getXHR()`

It returns the XHR object.

 * **Returns:** The constructor function of the XMLHttpRequest object.

##### `setRequestUrl(url)`

Set the URL for the request

 * **Parameters:** `url` — The URL to send the request to.
 * **Returns:** The `setRequestUrl` method returns the `this` object.

##### `getRequestUrl()`

Get the URL of the request

 * **Returns:** The URL of the request.

##### `setCallbackEverywhere(func)`

Set a callback function that will be called for every request

 * **Parameters:** `func` — The function to be called when the request is complete.
 * **Returns:** The `ajax` function.

##### `getCallbackEverywhere()`

*Returns* the callback function that is used to process the response from the server

 * **Returns:** The callback function that is set to be called on every request.

##### `request(everywhere)`

It sends a POST request to the server.

 * **Parameters:** `everywhere` — Boolean. If true, the callback will be called for every request. If

     false, the callback will only be called for the first request.
 * **Returns:** Nothing 

##### `error()`

If the request fails, try again

##### `load()`

* Load the JSON data from the server. * If the JSON data is valid, call the success callback function. * If the JSON data is invalid, call the fail callback function

 * **Returns:** `alse` — 

##### `handleEvent(event)`

If the event type is a function defined in the object, call that function

 * **Parameters:** `event` — The event object that was passed to the handler.
 * **Returns:** The callable event.

##### `static collapse(object)`

Collapse all nested objects into a single level object

 * **Parameters:** `object` — The object to be collapsed.
 * **Returns:** The object that is being collapsed.

## Built With

* [Javascript](https://www.javascript.com/) - Javascript

## Contributing

Please read [CONTRIBUTING.md](https://github.com/energia-source/widget-xkr/blob/main/CONTRIBUTING.md) for details on our code of conduct, and the process for submitting us pull requests.

## Versioning

We use [SemVer](https://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/energia-source/widget-xkr/tags). 

## Authors

* **Paolo Fabris** - *Initial work* - [energia-europa.com](https://www.energia-europa.com/)
* **Gabriele Luigi Masero** - *Developer* - [energia-europa.com](https://www.energia-europa.com/)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details