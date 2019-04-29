`from orm_practice import \*`  
`s = Store(name="Meng's Camera Store")`  
`s.save()`

`wh1 = Warehouse(location="Damansara", store=s)`  
`wh1.save()`

`wh2 = Warehouse(location="KLCC", store=s)`  
`wh2.save()`

`p = Product(name="MacBook Pro", description="An expensive laptop", warehouse=wh1)`
