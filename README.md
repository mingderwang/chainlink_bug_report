# chainlink_bug_report

* in [http.go](https://github.com/smartcontractkit/chainlink/blob/master/core/adapters/http.go) line 124 function appendExtendedPath() may change the url.Path.

* see testing on golang playground: https://play.golang.org/p/tV87gXCuu8e
That cause the problem and get the following API get no JSON return.

* for example this API as example: https://api.nasa.gov/insight_weather/?api_key=eTitgeQIgcVYEqKbEfToPyG1r1GVVbaV4SKC7vwe&feedtype=json&ver=1.0

or  https://api.nasa.gov/insight_weather/?api_key=DEMO_KEY&feedtype=json&ver=1.0

```
https://api.nasa.gov/insight_weather/?api_key=eTitgeQIgcVYEqKbEfToPyG1r1GVVbaV4SKC7vwe&feedtype=json&ver=1.0
```
the url.PATH had been changed to the one without "/" slash after insight_weather, that cause no JSON data in return.
```
https://api.nasa.gov/insight_weather?api_key=eTitgeQIgcVYEqKbEfToPyG1r1GVVbaV4SKC7vwe&feedtype=json&ver=1.0
```
