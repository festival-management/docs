# Subcategories

Il modello Subcategory rappresenta un'entità che definisce una "sotto-categoria" all'interno del sistema. Una 
sotto-categoria possiede alcune caratteristiche tra cui l'id, il nome e l'ordine. L'ordine è una proprietà numerica che 
serve a definire in fase di stampa dell'ordine in che posizione stampare tutti i prodotti di quella specifica 
sotto-categoria.

Una sotto-categoria rappresenta un "contenitore" per tutti i prodotti che contiene: un esempio possono essere i primi, 
secondi, birre, vino. Nella comanda i primi avranno ordine 1, i secondi ordine 2, e così via...

## Attributi del Modello `Subcategory`:
```python
class Subcategory(BaseModel):
    id: int
    name: str
    order: int
```
- **id**: l'identificativo univoco della sotto-categoria. Ogni sotto-categoria ha un id che lo distingue da altre 
  sotto-categorie nel sistema.
- **name**: il nome della sotto-categoria. Deve essere unica nel sistema.
- **order**: l'ordine della sotto-categoria in fase di stampa della comanda.