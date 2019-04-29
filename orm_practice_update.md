## Your objectives:

1. A product was sold, delete the product
2. Business isn't going well, delete a warehouse

```python
from orm_practice import *
```

```python
db.connect()
```

    True

```python
q = Product.update({Product.warehouse_id: 2}).where(Product.id == 1)
```

```python
q.execute()
```

    1

## Your objectives:

1. A product was sold, delete the product
2. Business isn't going well, delete a warehouse

```python
d = Product.delete().where(Product.id == 1)
```

```python
d.execute()
```

    1

```python
d = Warehouse.delete().where(Warehouse.id == 1)
```

```python
d.execute()
```

    1

```python

```
