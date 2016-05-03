# KnotenSchieber
Erzeugt eine Liste mit allen Knoten für die fastd Blacklist. Knoten können  so auf andere Server geschoben werden.

Kommando:
```
socat - UNIX-CONNECT:/var/tmp/fastd.ffld.sock | jq '.peers | keys | { pubkey : .[] , comment : "shift to other server" ,}' | sed ':a;N;$!ba;s/}\n{/},\n{ /g'
```
