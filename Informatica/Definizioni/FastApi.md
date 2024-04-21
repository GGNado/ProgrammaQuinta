- Un Framework che ci permette di creare API web
- Usato in python -> [[Python base generale]]
Creiamo oggetto API e attraverso decoratori (@ con il nome) noi diciamo sotto quale rotta gira una determinata funzione. 

```python:
@webapp.get("api/persone")
async def getAllPersone():
	#Chiamata a funzione del database
```