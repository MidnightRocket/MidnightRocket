I MidnightRocket use the following key structure:
A root of trust key:
```
pub	rsa4096/F9B8BB160BBCC79C 2022-05-09 [SC]
	Key fingerprint = 4D83 0275 D62C 5184 4463  7155 F9B8 BB16 0BBC C79C
uid		MidnightRocket (Long-term Root key) <45201103+MidnightRocket@users.noreply.github.com>
```

And a daily use key:
```
pub	ed25519/DA1FD6C6670E36D7 2022-05-09 [SC] [expires: 2023-05-09]
	Key fingerprint = DBFB 2472 B397 7CD7 93FE  A9D1 DA1F D6C6 670E 36D7
uid		MidnightRocket (Daily usage key) <45201103+MidnightRocket@users.noreply.github.com>
sub	cv25519/A2443C54AF560EC2 2022-05-09 [E] [expires: 2023-05-09]
sub	ed25519/CBCE0BC869046ECE 2022-05-09 [A] [expires: 2023-05-09]
```


The `Long-term Root key` is used only to sign special statements like this one, and to sign keys that I personally am in control of.
This key was generated in an air-gaped environment, and then imported to an OpenPGP smart card, to perform signatures on less secure systems. The smart card is kept physically secure, and is only taken out of storage when needed.

The `Daily usage key` is also generated in an air-gaped environment, and imported to another OpenPGP smart card. This key is carried around, and is used in daily operations, like signing commits etc. This key is naturally more susceptible to loss or theft, than the `Long-term Root key`. In case of loss or theft the `Long-term Root key` can be used to establish trust in a new `Daily usage key`.

I use this scheme over the 'separated main and sub keys', as I think it is a more flexible approach.



<br><br>
I have previously used another GPG key, to sign a few commits. This key will no longer be used, and is superseded by the above mentioned keys.
```
pub	rsa4096/0B55A05E1C7C8E9F 2019-03-14 [SC] [Revoked]
	Key fingerprint = FE0A ED47 F307 E4C8 D821  FCF7 0B55 A05E 1C7C 8E9F
uid		MidnightRocket (For signing git commits locally) <45201103+MidnightRocket@users.noreply.github.com>
sub	rsa4096/0BA49EF81A951FFD 2019-03-14 [E] [Revoked]
sub	rsa4096/4DEC3C79F7BEC01E 2019-03-18 [S] [Revoked]
```