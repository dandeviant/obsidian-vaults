### Base64

Encoding
```bash
$ echo hellothere | base64
aGVsbG90aGVyZQo=
```

Decoding
```bash
$ echo aGVsbG90aGVyZQo= | base64 -d
hellothere
```

---

### ROT13
```bash
sudo apt-get install hxtools
```

```bash
$ echo "hello" | rot13                                                             
uryyb
```


