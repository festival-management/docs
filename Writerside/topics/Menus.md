# Menus

Il modello Menu rappresenta un'entità che definisce un "menù" all'interno del sistema. Questo menù è associato a una 
lista di date in cui il menù è valido, a una lista di ruoli che possono ordinare un determinato menù e a una lista di 
campi.

## Date
Un menù contiene una lista di date per cui quel menù è valido, solo se la data del server si trova in un range
di validità del menù allora un utente con permesso `can_order` potrà ordinare tale menù. Un utente con permesso
`can_administer` può vedere tutti i menù in ogni momento.

**Esempio**: Se un menù è valido dal 1 gennaio al 31 gennaio e dal 1 marzo al 15 marzo, un utente che tenta di
ordinare il menù il 2 febbraio non sarà in grado di farlo.

### Attributi del Modello `MenuDate`:
```python 
class MenuDate(BaseModel):
    id: int
    start_date: datetime.datetime
    end_date: datetime.datetime
```
- **id**: l'identificativo univoco della data di un menù. Ogni data ha un id che lo distingue da altre date nel
  sistema.
- **start_data**: data iniziale del range per menù.
- **end_date**: data finale del range per menù.

## Campi
Un menù contiene una lista di campi, un campo ha un nome, il numero massimo di elementi che si possono ordinare (una 
volta superato questo numero verrà aggiunto un prezzo a ogni prodotto che si aggiunge), un attributo per specificare se 
è opzionale (se è obbligatorio dovrà essere presente per ogni menù ordinato). Inoltre possiede una lista di prodotti, 
ogni prodotto ha un prezzo (può essere anche 0) che verrà aggiunto se viene selezionato il prodotto al momento 
dell'ordine.

**Esempio**: Il menù panino (è un menù perché contiene più prodotti al suo interno) avrà un campo "pane" che sarà 
obbligatorio con numero massimo di elementi ordinabili pari a 1 e al suo interno conterrà il pane o piadina.

### Attributi del Modello `MenuField`:
```python 
class MenuFieldProduct(BaseModel):
    id: int
    price: float
    product: Product


class MenuField(BaseModel):
    id: int
    name: str
    max_sortable_elements: int
    additional_cost: float
    is_optional: bool
    products: list[MenuFieldProduct] | None = None
```
- **id**: l'identificativo univoco del campo di un menù. Ogni campo ha un id che lo distingue da altri campi nel
  sistema.
- **name**: nome del campo.
- **max_sortable_elements**: numero massimo di elementi che si possono ordinare per campo (una volta superata la soglia 
  verrà aggiunto per ogni elemento che supera la soglia il prezzo contenuto in `additional_cost`).
- **additional_cost**: prezzo da moltiplicare per il numero di elementi che superano la soglia `max_sortable_elements`.
- **is_optional**: specifica se il campo è opzionale oppure è obbligatorio.
- **products**: lista di prodotti del campo.
  - **price**: ogni prodotto ha un prezzo (può essere anche 0) perché volendo se si seleziona uno specifico prodotto del
    campo il prezzo può variare.

## Ruoli
Un menù, inoltre, contiene una lista di ruoli. Solo un utente il cui ruolo è presente nella lista di ruoli del menù 
potrà ordinare quello specifico menù. Un ruolo, per essere dentro la lista di ruoli di un menù deve avere il permesso 
`can_order`.

**Esempio**: Un menù può essere ordinato solo da utenti con il ruolo di "cassa1" o "cassa2", a condizione che
abbiano il permesso `can_order`.

### Attributi del Modello `MenuRole`:
```python 
class MenuRole(BaseModel):
    id: int
    role_id: int
```
- **id**: l'identificativo univoco del ruolo di un menù. Ogni ruolo ha un id che lo distingue da altri ruoli nel
  sistema.
- **role_id**: id del ruolo presente per il singolo menù (per singolo menù non potranno esserci più ruoli con lo
  stesso id).

## Attributi del Modello `Menu`:
```python 
class Menu(BaseModel):
    id: int
    name: str
    short_name: str
    price: float
    dates: list[MenuDate] | None = None
    fields: list[MenuField] | None = None
    roles: list[MenuRole] | None = None
```
- **id**: l'identificativo univoco del menù. Ogni menù ha un id che lo distingue da altri menù nel sistema.
- **name**: il nome del menù. Deve essere unico nel sistema.
- **short_name**: nome corto del menù. Usato al momento della stampa (per occupare meno spazio).
- **price**: prezzo del menù.
- **dates**: array di date per la validità del menù (spiegato sopra).
- **fields**: array di campi del menù (spiegato sopra).
- **roles**: array di ruoli del menù (spiegato sopra).