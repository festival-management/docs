# Orders

Il modello Order rappresenta un'entità che definisce un "ordine" all'interno del sistema. Questo ordine è associato a un
nome del cliente, al numero di persone a cui è rivolto l'ordine, se è un ordine per asporto, il numero del tavolo, 
all'utente che effettua l'ordine, a una lista di menù ordinati, a una lista di prodotti ordinati e alla data di 
creazione dell'ordine. Se l'ordine è per asporto non è necessario specificare il numero di persone e il numero del 
tavolo.

## Prodotti
Un ordine contiene una lista di prodotti che il cassiere ha ordinato per uno specifico ordine.

### Attributi del Modello `OrderProduct`:
```python 
class OrderProductIngredient(BaseModel):
    id: int
    product_ingredient_id: int
    quantity: int


class OrderProduct(BaseModel):
    id: int
    product_id: int
    price: float
    quantity: int
    variant_id: int | None = None
    order_menu_field_id: int | None = None
    product: Product | None = None
    ingredients: list[OrderProductIngredient] | None = None
```
- **id**: l'identificativo univoco del prodotto di un ordine. Ogni prodotto ha un id che lo distingue da altri prodotti 
  nel sistema.
- **product_id**: id del prodotto ordinato.
- **price**: prezzo del prodotto ordinato.
- **quantity**: quantità del prodotto ordinato.
- **variant_id**: id della variante del prodotto ordinato (non obbligatorio se il prodotto non ha delle varianti).
- **order_menu_field_id**: id del campo del menù ordinato. Se il prodotto fa parte di un menù ordinato sarà presente 
  questo campo che fa riferimento all'ordine del menù.
- **product**: riferimento al prodotto.
- **ingredients**:
  - **id**: l'identificativo univoco dell'ingrediente di un prodotto ordinato. Ogni ingrediente ha un id che lo 
    distingue da altri ingredienti di un prodotto ordinato nel sistema.
  - **product_ingredient_id**: id dell'ingrediente del prodotto.
  - **quantity**: quantità dell'ingredienti ordinato.

## Menù
Un ordine contiene una lista di menù che il cassiere ha ordinato per uno specifico ordine.

### Attributi del Modello `OrderMenu`:
```python 
class OrderMenuField(BaseModel):
    id: int
    menu_field_id: int
    products: list[OrderProduct] | None = None


class OrderMenu(BaseModel):
    id: int
    price: float
    quantity: int
    menu: Menu | None = None
    fields: list[OrderMenuField] | None = None
```
- **id**: l'identificativo univoco del menù di un ordine. Ogni menù ha un id che lo distingue da altri menù nel sistema.
- **price**: prezzo del menù ordinato.
- **quantity**: quantità del menù ordinato.
- **menu**: riferimento al menù.
- **fields**:
  - **id**: l'identificativo univoco del campo di un menù ordinato. Ogni campo ha un id che lo distingue da altri campi
    di un menù ordinato nel sistema.
  - **menu_field_id**: id del campo del menù.
  - **products**: lista con tutti i prodotti ordinati per lo specifico campo. (riferimento a `OrderProduct` spiegato 
    sopra).

## Attributi del Modello `Order`:
```python 
class Order(BaseModel):
    id: int
    customer: str
    guests: int | None = Field(ge=1, default=None)
    is_take_away: bool
    table: int | None = Field(ge=1, default=None)
    user: User | None = None
    menus: list[OrderMenu] | None = None
    products: list[OrderProduct] | None = None
    created_at: datetime.datetime
```
- **id**: l'identificativo univoco dell'ordine. Ogni ordine ha un id che lo distingue da altri ordini nel sistema.
- **customer**: nome del cliente.
- **guests**: numero di persone (non obbligatorio se per asporto).
- **is_take_away**: specifica se l'ordine è per asporto.
- **table**: numero del tavolo (non obbligatorio se per asporto).
- **user**: riferimento all'utente che ha effettuato l'ordine.
- **menus**: lista di menù ordinati (riferimento a `OrderMenu` spiegato sopra).
- **products**: lista di prodotti ordinati (riferimento a `OrderProduct` spiegato sopra).
- **created_at**: data e ora di creazione dell'ordine.
