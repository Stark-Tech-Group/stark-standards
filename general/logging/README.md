<table>
  <thead>
    <tr>
      <th>Code</th><th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr><td> log-1  </td><td><strong>Do not serialize objects in a log message</strong>

```javascript
//avoid:
var thing = ["1", "2", "three"];
log.infof("current thing: %v", thing);
log.infof("current thing [%s]", thing.someField);
```

```javascript
//embrace:
var thing = ["1", "2", "three"];
log.infof("current thing size [%d]", thing.length);
```
</td></tr>

<tr><td> log-2  </td><td><strong>Do not log passwords or PII (Personal data)</strong></td></tr>

<tr><td> log-3  </td><td><strong>Do not provide your own log severity level, use the loggers severity levels</strong>

```javascript
//avoid:
log.info("ERROR: bad input");
```

```javascript
//embrace:
log.error("bad input");
```
</td></tr>

<tr><td> log-4  </td><td><strong>Do not provide your own log timestamp, use the loggers timestamp</strong>

```javascript
//avoid:
log.errorf("[%s] bad input", time.now());
```

```javascript
//embrace:
log.error("bad input");
```

<tr><td> log-5  </td><td><strong>Log message in UTC timezone</strong>

```javascript
//avoid:
log.setTimezone(Timezone.EST)
log.info("my special log message from EST");
```
</td></tr>

<tr><td> log-6  </td><td><strong>Wrap variables in brackets</strong><br/><br/>
Why: The brackets will provide some clues into the boundaries of a variable and if there are any trailing spaces or non-breaking characters.

```javascript
//avoid:
var title = "my title "
log.infof("the title is %s", title);
//ouput is 'the title is my title '
```

```javascript
//embrace:
var title = "my title "
log.infof("the title is [%s]", title); 
// output is 'the title is [my title ]' and you see the extra space more clearly
```
</td></tr>

<tr><td> log-7  </td><td><strong>Do not concatenation string, use string formatters</strong>

```javascript
//avoid:
log.info("status [" + "0" + "]");
```

```javascript
//embrace:
log.infof("status [%d]", 0);
```
</td></tr>

<tr><td> log-8  </td><td><strong>Use ISO timestamp format (YYYY-MM-DDTHH:MM:SS.mmm) when required to log a timestamp</strong></td></tr>

<tr><td> log-9  </td><td><strong>Use log levels appropriately</strong>
<ul>
<li><strong>TRACE level:</strong> this is a code smell if used in production. This should be used during development to track bugs, but never committed to your VCS.</li>
<li><strong>DEBUG level:</strong> log at this level about anything that happens in the program. This is mostly used during debugging, and I’d advocate trimming down the number of debug statement before entering the production stage, so that only the most meaningful entries are left, and can be activated during troubleshooting.</li>
<li><strong>INFO level:</strong> log at this level all actions that are user-driven, or system specific (ie regularly scheduled operations…)</li>
<li><strong>WARN level:</strong> log at this level all events that could potentially become an error. For instance if one database call took more than a predefined time, or if an in-memory cache is near capacity. This will allow proper automated alerting, and during troubleshooting will allow to better understand how the system was behaving before the failure.</li>
<li><strong>ERROR level:</strong> log every error condition at this level. That can be API calls that return errors or internal error conditions.</li>
<li><strong>FATAL level</strong>: too bad, it’s doomsday. Use this very scarcely, this shouldn’t happen a lot in a real program. Usually logging at this level signifies the end of the program. For instance, if a network daemon can’t bind a network socket, log at this level and exit is the only sensible thing to do.</li>
</ul>
</td></tr>

<tr><td> log-10  </td><td><strong>When available, log application name and version at startup</strong>

```javascript
//avoid:
log.infof("starting app:[%s] version:[%s]", env.GetAppName(), env.GetAppVersion());
```

</td></tr>
<tr><td> log-11  </td><td><strong>When available, log environment variables (non-sensitive) on startup</strong>

```javascript
//avoid:
log.infof("loading env var [%s] with value [%s]", env.KEY, os.getenv(env.KEY));
```

</td></tr>

<tr><td> log-12  </td><td><strong>Use configuration to set log levels, do not set log levels at compile time</strong><br/><br/>
Why: log levels should come from an environment variable or from a configuration file or system. If the log level is set at compile time, it requires a new build to change.

```javascript
//avoid:
log.setLevel(TRACE)
```

```javascript
//embrace:
log.setLevel(env.GetLogLevel())
```
</td></tr>

<tr><td> log-13  </td><td><strong>Provide enough detail</strong><br/><br/>
Why: In a system with many services running and log aggregation in place over all service, it is important to 
provide enough detail to help debug and trace a specific error.

```javascript
//avoid:
log.error("something went wrong")
```

```javascript
//embrace:
log.errorf("[%s] failed due to exceded timeout of [%d] ", "getCustomers", timeout)
```
</td></tr>


<tr><td> log-15  </td><td><strong>Avoid long log message with needless information</strong><br/><br/>

```javascript
//avoid:
log.error("the getUser call generated a bad request this is probably caused by some bad parameters")
```

```javascript
//embrace:
log.errorf("bad request [%s]", "getUser")
```
</td></tr>

<tr><td> log-16  </td><td><strong>Use consistent messages and/or message templates when available</strong><br/><br/>

```javascript
//avoid: different log formats for same kind of message
func getUser(i: number) 
{
    log.tracef("calling getUser with arg: [%d]", i);
        ...
}

func getCustomer(i: number)
{
    log.tracef("get customer with id [%d]", i);
...
}
```

```javascript
//avoid: different log formats for same kind of message
func getUser(i: number)
{
    log.tracef(GetLogTemplate(functionCall), "getUser", i);
...
}

func getCustomer(i: number)
{
    log.tracef(GetLogTemplate(functionCall), "getCustomer", i);
...
}
```
</td></tr>

</tbody>
</table>
