<table>
  <thead>
    <tr>
      <th>Code</th><th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr><td> sec-1  </td><td> Do not allow cross-site scripting (XSS) vulnerabilities</td></tr>
<tr><td> sec-2  </td><td> Do not allow cross-site request forgery (CSRF) vulnerabilities</td></tr>
<tr><td> sec-3  </td><td> Do not allow sql injection vulnerabilities, favor prepared statements and named variables

```javascript
//avoid:
function getUser(username) {
   return sql.getRows("SELECT id, username FORM users WHERE = '" + username + "'")
}
```

```javascript
//embrace:
function getUser(username) {
   return sql.getRows("SELECT id, username FORM users WHERE username = :username", {'username':username})
}
```
</td></tr>
<tr><td> sec-4  </td><td> Do not commit secrets to source control</td></tr>
<tr><td> sec-5  </td><td> Use a secrets manager</td></tr>
<tr><td> sec-6  </td><td> Do not log secrets
  
```javascript
//avoid:
function call(url, apiKey) {
  Logger.info("call with apiKey:" + apiKey)
  return url.setHeader("auth", apiKey).get(url)
}
```
  
</td></tr>
<tr><td> sec-7  </td><td> Treat Personal Identifiable Information (PII) as secrets</td></tr>
<tr><td> sec-8  </td><td> Always assume inputs will be malicious</td></tr>
<tr><td> sec-9  </td><td> Always assume file uploads will be malicious in content, size and type</td></tr>
<tr><td> sec-10 </td><td> Do not include secrets in error or exception messages</td></tr>
<tr><td> sec-11 </td><td> Use well known encryption tools. Don't create your own encryption algorithm</td></tr>
<tr><td> sec-12 </td><td> Avoid keeping secrets in memory longer than needed</td></tr>
<tr><td> sec-13 </td><td> Favor char arrays over strings for when storying secrets in memory</td></tr>
<tr><td> sec-14 </td><td> Protect against arithmetic overflow and underflow</td></tr>
<tr><td> sec-15 </td><td> Limit the count and size a log file can grow to</td></tr>
<tr><td> sec-16 </td><td> Configure XML parsers to prevent XXE</td></tr>
<tr><td> sec-17 </td><td> Never store secrets or PII in plain text</td></tr>
<tr><td> sec-18 </td><td> Limit serialization interfaces and protect against unsafe de-serialization vulnerabilities</td></tr>
<tr><td> sec-19 </td><td> HTTPS by default</td></tr>
<tr><td> sec-20 </td><td> Assume supply chains and vendors are compromised</td></tr>
<tr><td> sec-21 </td><td> Assume parsers are vulnerabilities (HTML, CSV, XML, JSON, REGEX, etc.)</td></tr>
<tr><td> sec-22 </td><td> Limit the number of chained exceptions</td></tr>
<tr><td> sec-23 </td><td> Log failed access and authentication attempts</td></tr>
<tr><td> sec-24 </td><td> Favor deny all</td></tr>
<tr><td> sec-25 </td><td> Document trusted IP address in net-sec repository</td></tr>
<tr><td> sec-26 </td><td> Document malicious IP addresses in net-sec repository</td></tr>
<tr><td> sec-27 </td><td> Limit number of failed access and authentication attempts</td></tr>
<tr><td> sec-28 </td><td> Throttle login to help prevent brute force

```javascript
//avoid:

// client-side
function login(creds) {
  return authService.auth(creds)  
}

// server-side:
function auth(creds) {
  return doAuth(creds)
}

```

```javascript
//embrace:

// client-side
function login(creds) {
  return authService.auth(creds)  
}

// server-side:
function auth(creds) {
  wait(1000)
  return doAuth(creds)
}

```

$(window).on('scroll', _.debounce(doSomething, 200));
  
</td></tr>
<tr><td> sec-29 </td><td> Do not store secrets in containers</td></tr>
</tbody>
