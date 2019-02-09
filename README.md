# compromised-keys
A random collection of compromised cryptographic keys.

## X.509 certificates
### Proof of compromise
By using a certificate's private key to sign the string "revoke", the obtained signature can be used as a proof of compromise without requiring additional distribution of the private key. For a certificate with the crt.sh ID "123456789", the following command can be used to create a proof of compromise signature:
``` bash
openssl dgst -sha256 -sign ./x509/123456789.key -out ./x509/123456789.revoke <(echo -n 'revoke')
```

The signature can be verified using the following command:
``` bash
openssl dgst -sha256 -verify <(openssl x509 -in ./x509/123456789.crt -pubkey -noout) -signature ./x509/123456789.revoke <(echo -n 'revoke')
```

| Date | crt.sh | Certificate | Proof of compromise | Issuer | Notes |
| --- | --- | --- | --- | --- | --- |
| 2019-02-09 | [252685801](https://crt.sh/?id=252685801) | [252685801](/x509/252685801.crt) | [252685801](/x509/252685801.revoke) | Go Daddy Secure Certificate Authority - G2 | [Source](https://twitter.com/duniel_pls/status/1093565709630824448) |
| 2019-02-09 | [307506564](https://crt.sh/?id=307506564) | [307506564](/x509/307506564.crt) | [307506564](/x509/307506564.revoke) | Go Daddy Secure Certificate Authority - G2 | [Source](https://twitter.com/duniel_pls/status/1093565709630824448), certificate expired |
| 2019-02-09 | [131620736](https://crt.sh/?id=131620736) | [131620736](/x509/131620736.crt) | [131620736](/x509/131620736.revoke) | GeoTrust SSL CA - G3 | [Source](https://twitter.com/duniel_pls/status/1093565709630824448), certificate revoked |
| 2019-02-09 | [237656393](https://crt.sh/?id=237656393) | [237656393](/x509/237656393.crt) | [237656393](/x509/237656393.revoke) | GeoTrust SSL CA - G3 | [Source](https://twitter.com/duniel_pls/status/1093565709630824448), certificate revoked |
| 2019-02-09 | [242296047](https://crt.sh/?id=242296047) | [242296047](/x509/242296047.crt) | [242296047](/x509/242296047.revoke) | Starfield Secure Certificate Authority - G2 | [Source](https://twitter.com/duniel_pls/status/1093565709630824448) |

