# API Overview

## Introduzione

Il principale obiettivo del gestionale è garantire una corretta ordinazione dei prodotti e dei menù, semplificando il 
processo di gestione per gli organizzatori e i partecipanti. Il software offre una serie di pagine intuitive che 
permettono di aggiungere e gestire facilmente i prodotti, i menù e gli utenti tramite un'interfaccia grafica 
user-friendly.

Il backend del sistema è stato sviluppato in Python, sfruttando la libreria FastAPI per garantire alte prestazioni e 
scalabilità. Il frontend è stato realizzato in TypeScript utilizzando il framework React, per offrire un'esperienza 
utente fluida e reattiva. Tutto il sistema è supportato dal robusto DBMS PostgreSQL, che assicura una gestione 
efficiente e sicura dei dati.

Il gestionale è quindi un sistema completo e integrato che semplifica la gestione delle ordinazioni e delle risorse, 
migliorando l'efficienza e la precisione nelle operazioni quotidiane della sagra.

## Autentificazione

Il sistema utilizza OAuth2 per l'autenticazione degli utenti. OAuth2 è un protocollo sicuro e potente che consente 
l'autenticazione senza dover condividere credenziali sensibili. Questo protocollo limita l'accesso alle risorse protette
attraverso l'emissione di access token, che rappresentano i permessi concessi all'utente.

Ogni volta che l'utente effettua una richiesta a risorse protette, è necessario includere l'access token 
nell'intestazione della richiesta. Questo token certifica che l'utente ha i permessi necessari per accedere a quella 
risorsa. Nel nostro sistema, l'access token contiene le seguenti informazioni:
```python
user_id: int
role_id: int
permissions: dict[str, bool]
exp: int = None
```
- <b>user_id</b>: L'ID univoco dell'utente, che permette di identificarlo nel sistema.
- <b>role_id</b>: L'ID del ruolo associato all'utente, utile per determinare i privilegi e le restrizioni di accesso.
- <b>permissions</b>: Un dizionario che specifica i permessi dell'utente per determinate azioni o risorse
  (es. {"can_administer": True, "can_order": False}).
- <b>exp</b>: La data di scadenza del token, generata automaticamente al momento della generazione del token.

Per tutti gli endpoint che richiedono l'autentificazione, ho utilizzato una dipendenza (si trova in utils), creata da me
per verificare a ogni richiesta se è presente il token jwt e se è ancora valido:
```python
token: TokenJwt = Depends(validate_token)
```

## Gestione degli errori

Il sistema ha una gestione degli errori, si possono riscontrare vari tipi di errore:
1. <b>Errori di validazione</b> (Code 422):
    - Questi errori si verificano quando i dati forniti dall'utente non soddisfano i criteri o le aspettative del 
    sistema (ad esempio, un formato di input errato o valori mancanti).
    - Esempio: L'utente inserisce un indirizzo email non valido.
    - Codice di risposta: 422 Unprocessable Entity
2. <b>Errori interni</b> (Code 500):
    - Questi errori si presentano quando il backend ottiene un errore processando i dati dell'utente.
    - Esempio: Si verifica un'eccezione non gestita durante un'operazione di scrittura su database (ad esempio, se la 
   connessione al database fallisce).
    - Codice di risposta: 500 Internal Server Error
3. <b>Errori custom</b> (code 4xx):
    - Questi errori si presentano in svariate circostanze, e sono tutti gli errori che gestisce il backend con gli 
    errori 4xx.
    - Esempio: Autentificazione fallita, prodotto non valido, ecc.
    - Codice di risposta: 4xx (ad esempio, 401 Unauthorized, 403 Forbidden, 404 Not Found)

Tutti gli errori si trovano nel seguente formato:
```python
error: bool = True
code: int
```
- <b>Code</b>: Un intero che rappresenta il tipo specifico di errore. Il codice di errore fa riferimento a un enum che 
  raccoglie tutti i possibili errori nel sistema. Ogni codice di errore è associato a una specifica condizione o 
  problema.

> **Futuro aggiornamento:**
> 
> In un futuro aggiornamento, sarà introdotta una gestione più dettagliata degli errori. Questo miglioramento consentirà 
> di includere informazioni aggiuntive, come la descrizione del dato specifico all'interno di una sequenza di dati che 
> ha causato l'errore. In questo modo, gli sviluppatori e gli utenti finali saranno in grado di individuare con maggiore 
> precisione la causa dell'errore e adottare le azioni correttive necessarie.
{style="note"}

