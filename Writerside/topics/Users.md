# Users

Il modello User rappresenta un'entità che definisce un "utente" all'interno del sistema. Un utente è associato a un 
ruolo, inoltre possiede alcune caratteristiche tra cui l'id, l'username, la password, e la data di creazione.

La password dell'utente è trattata in modo sicuro: nel database è memorizzata sotto forma di hash utilizzando 
l'algoritmo `argon2id`. Durante il login, la password viene inviata dal client per essere confrontata con l'hash nel 
database, ma una volta autenticato, l'utente non invia più la password.

## Attributi del Modello `User`:
```python 
class User(Model):
    id: int
    username: str
    password: str
    role: Role
    created_at: datetime.datetime
```
- **id**: l'identificativo univoco dell'utente. Ogni utente ha un id che lo distingue da altri utenti nel sistema.
- **username**: l'username univoco dell'utente, utilizzato per il login. Deve essere unico nel sistema.
- **password**: la password dell'utente, memorizzata come hash nel database utilizzando l'algoritmo `argon2id`. La 
  password non viene mai archiviata in chiaro. Durante il login, la password inviata viene confrontata con l'hash per 
  l'autenticazione.
- **role**: ruolo dell'utente in questione, l'utente assumerà tutte le impostazioni del ruolo (permessi, ecc.).
- **created_at**: data e ora della creazione dell'utente.

## Password
La password frutta l'algoritmo di hashing `argon2id` per evitare attacchi di tipo brute force e rainbow table grazie 
all'uso di un costante "salt" e alla possibilità di regolare la difficoltà dell'hashing (fattore di iterazione).