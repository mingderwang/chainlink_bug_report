# chainlink_bug_report

* in line 124 https://github.com/smartcontractkit/chainlink/blob/7391acf38718659fb850f5b8c837f035a160b1f2/core/adapters/http.go, function appendExtendedPath() may change the url.Path.

* see testing on golang playground: https://play.golang.org/p/tV87gXCuu8e
That cause the problem and get the following API get no JSON return.

* for example this API as example: https://api.nasa.gov/insight_weather/?api_key=eTitgeQIgcVYEqKbEfToPyG1r1GVVbaV4SKC7vwe&feedtype=json&ver=1.0

or  https://api.nasa.gov/insight_weather/?api_key=DEMO_KEY&feedtype=json&ver=1.0
