## Blind SQLi script

For single url:
```sh
python3 lostsec.py -u "http://testphp.vulnweb.com/artists.php?artist="  -p payloads/xor.txt -t 5
```

for multiple urls:

```sh
python3 lostsec.py -l final.txt -p payloads/xor.txt -t 5
```
