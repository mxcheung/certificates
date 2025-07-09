
```
awk 'BEGIN {c=0;} /BEGIN CERT/ {c++} { print > ("cert" c ".pem") }' < fullchain.pem
```

```
openssl x509 -in cert1.pem -text -noout -nameopt multiline
openssl x509 -in cert2.pem -text -noout -nameopt multiline
```
