# Roles

Il modello Role rappresenta un'entità che definisce un "ruolo" all'interno del sistema. Questo ruolo è associato a 
permessi specifici che determinano quali azioni un utente con tale ruolo può eseguire nel sistema. Inoltre, il modello 
include un campo opzionale per la configurazione di una dimensione di carta predefinita.

## Attributi del Modello `Role`:
```python 
class Role(BaseModel):
    id: int
    name: str
    permissions: dict[Permission, bool]
    paper_size: PaperSize | None
```
- **id**: l'identificativo univoco del ruolo. Ogni ruolo ha un id che lo distingue da altri ruoli nel sistema.
- **name**: il nome del ruolo.
- **permissions**: un dizionario che associa a ogni permesso un valore booleano, che indica se il permesso è abilitato
  (True) o disabilitato (False) per il ruolo. I permessi definiscono quali operazioni un ruolo può o non può compiere 
  all'interno del sistema. I ruoli consentiti sono: `can_administer`, `can_order`, `can_statistics`, e 
  `can_priority_statistics`.
- **paper_size**: un campo che specifica la dimensione della carta predefinita per il ruolo, necessario se il ruolo può
  compiere ordini (specifica il formato della carta di stampa).

## Permessi:
```python 
class Permission(StrEnum):
    CAN_ADMINISTER = "can_administer"
    CAN_ORDER = "can_order"
    CAN_STATISTICS = "can_statistics"
    CAN_PRIORITY_STATISTICS = "can_priority_statistics"
```
- **can_administer**: permesso di eseguire tutte le operazioni di amministrazione. Questo ruolo lo possiede solo 
  l'utente `admin`, creato la prima volta che viene eseguito il backend.
- **can_order**: permesso di eseguire ordini (route `/orders/`), è possibile settare a True questo permesso solo e solo
  se è impostato un `paper_size` nel ruolo.
- **can_statistics**: con questo permesso, un utente con un ruolo che possiede questo permesso portà vedere tutte le
  statistiche.
- **can_priority_statistics**: con questo permesso, un utente con un ruolo che possiede questo permesso portà vedere le
  statistiche dei prodotti che possiedono `is_priority` a True.