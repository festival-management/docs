# Products

Il modello Product rappresenta un'entità che definisce un "prodotto" all'interno del sistema. Questo prodotto è 
associato a una lista di date in cui il prodotto è valido, a una lista di ruoli che possono ordinare un determinato 
prodotto, a una lista di ingredienti e una lista di varianti.

## Date
Un prodotto contiene una lista di date per cui quel prodotto è valido, solo se la data del server si trova in un range 
di validità del prodotto allora un utente con permesso `can_order` potrà ordinare tale prodotto. Un utente con permesso 
`can_administer` può vedere tutti i prodotti in ogni momento.

**Esempio**: Se un prodotto è valido dal 1 gennaio al 31 gennaio e dal 1 marzo al 15 marzo, un utente che tenta di 
ordinare il prodotto il 2 febbraio non sarà in grado di farlo.

### Attributi del Modello `ProductDate`:
```python 
class ProductDate(BaseModel):
    id: int
    start_date: datetime.datetime
    end_date: datetime.datetime
```
- **id**: l'identificativo univoco della data di un prodotto. Ogni data ha un id che lo distingue da altre date nel 
  sistema.
- **start_data**: data iniziale del range per prodotto.
- **end_date**: data finale del range per prodotto.

## Ingredienti
Un prodotto contiene una lista di ingredienti, al momento dell'ordine il cassiere avrà la possibilità di selezionare 
quali ingredienti includere nell'ordine. Ad esempio le patatine fritte possono avere come ingredienti la maionese, il
ketchup, ecc., e il cassiere potrà scegliere se includere o meno ciascun ingrediente. Ogni ingrediente selezionato 
potrebbe comportare un prezzo aggiuntivo.

**Nota**: Gli ingredienti sono opzionali e il loro prezzo può variare, incrementando il costo finale del prodotto.

### Attributi del Modello `ProductIngredient`:
```python 
class ProductIngredient(BaseModel):
    id: int
    name: str
    price: float
```
- **id**: l'identificativo univoco dell'ingrediente di un prodotto. Ogni ingrediente ha un id che lo distingue da altri 
  ingredienti nel sistema.
- **name**: nome dell'ingrediente, anche questo è univo per prodotto (non ci possono essere più ingredienti con lo 
  stesso nome per un prodotto).
- **price**: prezzo aggiuntivo se al momento dell'ordine si seleziona questo ingrediente (può essere anche 0).

## Ruoli
Un prodotto, inoltre, contiene una lista di ruoli. Solo un utente il cui ruolo è presente nella lista di ruoli del 
prodotto potrà ordinare quello specifico prodotto. Un ruolo, per essere dentro la lista di ruoli di un prodotto deve
avere il permesso `can_order`.

**Esempio**: Un prodotto può essere ordinato solo da utenti con il ruolo di "cassa1" o "cassa2", a condizione che 
abbiano il permesso `can_order`.

### Attributi del Modello `ProductRole`:
```python 
class ProductRole(BaseModel):
    id: int
    role_id: int
```
- **id**: l'identificativo univoco del ruolo di un prodotto. Ogni ruolo ha un id che lo distingue da altri ruoli nel
  sistema.
- **role_id**: id del ruolo presente per il singolo prodotto (per singolo prodotto non potranno esserci più ruoli con lo
  stesso id).

## Varianti
Un prodotto può avere una lista di varianti. Al momento dell'ordine, il cassiere potrà selezionare una variante del 
prodotto (questa operazione non è obbligatoria se il prodotto non possiede varianti). Le varianti possono riguardare, ad
esempio, le dimensioni di una bevanda (piccola, media, grande), e la selezione di una variante potrebbe comportare un 
prezzo aggiuntivo.

**Nota**: La selezione di una variante non è obbligatoria, ma può influire sul prezzo finale del prodotto.

### Attributi del Modello `ProductVariant`:
```python 
class ProductVariant(BaseModel):
    id: int
    name: str
    price: float
```
- **id**: l'identificativo univoco della variante di un prodotto. Ogni variante ha un id che lo distingue da altre
  varianti nel sistema.
- **name**: nome della variante, anche questo è univo per prodotto (non ci possono essere più varianti con lo
  stesso nome per un prodotto).
- **price**: prezzo aggiuntivo se al momento dell'ordine si seleziona questa variante (può essere anche 0).

## Attributi del Modello `Product`:
```python 
class Product(BaseModel):
    id: int
    name: str
    short_name: str
    is_priority: bool
    price: float
    category: Category
    subcategory_id: int
    dates: list[ProductDate] | None = None
    ingredients: list[ProductIngredient] | None = None
    roles: list[ProductRole] | None = None
    variants: list[ProductVariant] | None = None
```
- **id**: l'identificativo univoco del prodotto. Ogni prodotto ha un id che lo distingue da altri prodotti nel sistema.
- **name**: il nome del prodotto. Deve essere unico nel sistema.
- **short_name**: nome corto del prodotto. Usato al momento della stampa (per occupare meno spazio).
- **is_priority**: usato per le statistiche, ci sono ruoli con permesso `can_statistics_priority`, questi potranno 
  vedere solo i prodotti prioritari.
- **price**: prezzo del prodotto.
- **category**: categoria del prodotto, usata al momento della stampa per indirizzare i prodotti verso le stampanti 
  corrette.
- **subcategory_id**: sotto-categoria del prodotto.
- **dates**: array di date per la validità del prodotto (spiegato sopra).
- **ingredients**: array di ingredienti del prodotto (spiegato sopra).
- **roles**: array di ruoli del prodotto (spiegato sopra).
- **variants**: array di varianti del prodotto (spiegato sopra).