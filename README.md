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
# Handled via crafted HTTP redirect responses using netcat listener
nc -lnvp 1337
```

---

## 🟢 JavaScript Redirects

```bash
# Accessed redirected endpoint manually after inspecting JS response
curl http://challenge.localhost/<redirected-endpoint>
```

---

## 🟢 Including JavaScript

```bash
curl http://challenge.localhost/<javascript-resource>
```

---

## 🟢 HTTP (javascript)

```bash
# Triggered HTTP request via browser JavaScript execution
# (Observed and replicated request manually with curl)
```

---

## 🟢 HTTP GET Parameters (javascript)

```bash
curl "http://challenge.localhost/<endpoint>?param=value"
```

---

## 🟢 HTTP Forms (javascript)

```bash
curl -X POST -d "key=value" http://challenge.localhost/<endpoint>
```
