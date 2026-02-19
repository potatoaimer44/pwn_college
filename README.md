Here is a **professionally formatted GitHub-ready README.md** version of your writeup, structured cleanly for portfolio and internship visibility.

You can directly paste this into your repository’s `README.md`.

---

# 🌐 Web Exploitation & HTTP Protocol Challenges Writeup

This repository documents my solutions to multiple web-based challenges completed on **pwn.college**.

The exercises focus on:

* Crafting raw HTTP requests
* Understanding GET vs POST parameters
* Manipulating headers
* Cookie handling
* Session management
* Using tools like `curl`, `netcat`, and Python (`requests`, `urllib`)

---

## 📌 Environment & Tools Used

* `curl`
* `netcat (nc)`
* Python 3
* `requests` library
* `urllib`
* Manual HTTP request crafting

---

# 🧪 Challenge Writeups

---

## 1️⃣ HTTP GET Parameter Manipulation

### 💻 Command

```bash
curl "http://challenge.localhost/mission?hash=crwtzkzq"
```

### 🏁 Flag

```
pwn.college{Y2-O5hoV6tk5OCnakb47GNmN3sd.dBDOyMDL2gTN3QzW}
```

---

## 2️⃣ Manual GET Request via netcat

### 💻 Command

```bash
echo -ne "GET /verify?code=kevtdhdk&secure_key=gsktycvh&pin=kxdgtsph HTTP/1.1\r\nHost: challenge.localhost\r\nUser-Agent: Mozilla/5.0 Firefox/123.0\r\n\r\n" | nc challenge.localhost 80
```

### 🏁 Flag

```
pwn.college{kEh5IzxGAdVZ0oX5gBSUw5HZryn.dRDOyMDL2gTN3QzW}
```

---

## 3️⃣ Multiple GET Parameters

### 💻 Command

```bash
curl "http://challenge.localhost/hack?auth_key=pymvrrfi&auth_token=nzfnhrkj&unlock_code=tbcuydoh"
```

### 🏁 Flag

```
pwn.college{YhoG4ugGd3B3-w5C4aYyZY6HmA9.dNDOyMDL2gTN3QzW}
```

---

## 4️⃣ Basic POST Request

### 💻 Command

```bash
curl -X POST -H "User-Agent: Mozilla/5.0 Firefox/123.0" \
-d "challenge_key=dflwpptn" \
http://challenge.localhost/check
```

### 🏁 Flag

```
pwn.college{oWVovw81El_k2oWUZ9VoO06b5hJ.QX2EDO0EDL2gTN3QzW}
```

---

## 5️⃣ Form Data Submission

### 💻 Command

```bash
curl -X POST -H "User-Agent: Mozilla/5.0 Firefox/123.0" \
-d "access=ugchpjev" \
http://challenge.localhost/meet
```

### 🏁 Flag

```
pwn.college{QFhFPaVLtaoKU370ItN1IlfMccg.dZDOyMDL2gTN3QzW}
```

---

## 6️⃣ Manual POST Request (Raw HTTP)

### 💻 Command

```bash
echo -ne "POST /submit HTTP/1.1\r\nHost: challenge.localhost\r\nContent-Type: application/x-www-form-urlencoded\r\nContent-Length: 16\r\n\r\nkeycode=jrubmnnj" | nc challenge.localhost 80
```

### 🏁 Flag

```
pwn.college{Ijbc6_NBL7aZ_jEgy5OOmK-9QNI.ddDOyMDL2gTN3QzW}
```

---

## 7️⃣ Python `requests` POST

### 💻 Command

```bash
python3 -c "import requests; print(requests.post('http://challenge.localhost/entry', data={'pin': 'hcdwpugp'}).text)"
```

### 🏁 Flag

```
pwn.college{8cOY__YSvIm8v1kLD6QoKSHoVy3.dhDOyMDL2gTN3QzW}
```

---

## 8️⃣ Password Submission via POST

### 💻 Command

```bash
curl -X POST -H "User-Agent: Mozilla/5.0 Firefox/123.0" \
-d "password=fqafhyup" \
http://challenge.localhost/attempt
```

### 🏁 Flag

```
pwn.college{QVJw5yNcO7DyLSiReF436uqbNdU.QX3EDO0EDL2gTN3QzW}
```

---

## 9️⃣ Multiple POST Parameters

### 💻 Command

```bash
curl -X POST -H "User-Agent: Mozilla/5.0 Firefox/123.0" \
-d "authcode=ephxdzer&login_key=xxmiiqbf&auth_token=lkxritlg" \
http://challenge.localhost/trial
```

### 🏁 Flag

```
pwn.college{Ih1Jie_iUoDxYFWElkGiI3mnAQL.dlDOyMDL2gTN3QzW}
```

---

## 🔟 Advanced Raw POST

### 💻 Command

```bash
echo -ne "POST /qualify HTTP/1.1\r\nHost: challenge.localhost\r\nContent-Type: application/x-www-form-urlencoded\r\nContent-Length: 74\r\n\r\nsecret_key=kzhmmxji&code=ehqtbvue&credential=bvzuzfbd&access_code=vrjkrpnj" | nc challenge.localhost 80
```

### 🏁 Flag

```
pwn.college{IzavUWRrp2fRr2uv_RnQKpWk6Mv.dBTOyMDL2gTN3QzW}
```

---

## 1️⃣1️⃣ Hidden Endpoint Discovery

### 💻 Command

```bash
echo -ne "GET /erHXmyPc-fulfill HTTP/1.1\r\nHost: challenge.localhost\r\nUser-Agent: Mozilla/5.0 Firefox/123.0\r\n\r\n" | nc challenge.localhost 80
```

### 🏁 Flag

```
pwn.college{kE9ho2RCpdEGPKGrcyG88H5tRUZ.dlTOyMDL2gTN3QzW}
```

---

## 1️⃣2️⃣ Direct Endpoint Access

### 💻 Command

```bash
curl -H "User-Agent: Mozilla/5.0 Firefox/123.0" \
http://challenge.localhost/lYhqCPZG-evaluate
```

### 🏁 Flag

```
pwn.college{Iotl3JpmtnZpk-8scjNdgDGeVB1.dhTOyMDL2gTN3QzW}
```

---

## 1️⃣3️⃣ Python `urllib` Exploit

### 💻 Command

```bash
python3 -c "from urllib.request import urlopen; print(urlopen('http://challenge.localhost/xdpCOBtU-pwn').read().decode())"
```

### 🏁 Flag

```
pwn.college{47GetW6gSuHaJQudrO02terzyYK.dBDMzMDL2gTN3QzW}
```

---

## 🍪 Cookie Handling & Session Management

### 1️⃣4️⃣ Cookie Storage with curl

```bash
curl -c cookie.txt http://127.0.0.1:80
curl -b cookie.txt http://127.0.0.1:80
```

🏁 Flag:

```
pwn.college{8sv98yfpF6IXXjRTcGLoIjbHKIt.dFDMzMDL2gTN3QzW}
```

---

### 1️⃣5️⃣ Manual Cookie Injection

```bash
echo -ne "GET / HTTP/1.1\r\nHost: challenge.localhost\r\nCookie: cookie=e2e52106a00ec23dd76d34768d45a46d\r\n\r\n" | nc challenge.localhost 80
```

🏁 Flag:

```
pwn.college{kE8OQ1eS3s8OYUncyDWrArFcIZZ.dJDMzMDL2gTN3QzW}
```

---

### 1️⃣6️⃣ Python Session Handling

```bash
python3 -c "import requests;s = requests.Session();s.get('http://challenge.localhost/');print(s.get('http://challenge.localhost/flag').text)"
```

🏁 Flag:

```
pwn.college{Qq7Uh-qvPn2e3BJ1Ncwf3oB2FB0.dNDMzMDL2gTN3QzW}
```

---

### 1️⃣7️⃣ Multi-Step Authenticated Flow

```bash
python3 -c "import requests;s = requests.Session();r1 = s.get('http://challenge.localhost/');r2 = s.get('http://challenge.localhost/dashboard');print(s.get('http://challenge.localhost/flag').text)"
```

🏁 Flag:

```
pwn.college{AWBoz4ZlJIGbfRCyJ2N9pBzm0sY.dZDMzMDL2gTN3QzW}
```

---

## 🔌 Reverse Connection / Listener Challenge

### 💻 Command

```bash
nc -lnvp 1337
```

### 🏁 Flags Obtained

```
pwn.college{wWsCJ4bGVV89qsQ1PM4n6AvOQxA.QX5MDO0EDL2gTN3QzW}
pwn.college{k8YPMj9ZNPg6rQpttz34J24os2c.QXwQDO0EDL2gTN3QzW}
pwn.college{krbRHSJ75T02cxjSvw1-nZhvdYX.QX1EDM1EDL2gTN3QzW}
pwn.college{coH8_V1CYY3ypXEn2UzI__O96hF.QX2EDM1EDL2gTN3QzW}
pwn.college{ktfGqMQ65Du5fshsIxGifQrmW9-.QX3EDM1EDL2gTN3QzW}
pwn.college{QHTazhJm9mFNseHcvGTzVRFJY5o.QX4EDM1EDL2gTN3QzW}
pwn.college{w9cMGLMVWHJx8K9HRqZBzZRXjqA.QX5EDM1EDL2gTN3QzW}
```


