
# Step-by-step to view certificate and intermediate(s)
This will split the file into:
   cert1.pem (leaf certificate)
   cert2.pem (intermediate)
   cert3.pem (maybe another intermediate or root)
```
awk 'BEGIN {c=0;} /BEGIN CERT/ {c++} { print > ("cert" c ".pem") }' < fullchain.pem
```

```
openssl x509 -in cert1.pem -text -noout -nameopt multiline
openssl x509 -in cert2.pem -text -noout -nameopt multiline
```
