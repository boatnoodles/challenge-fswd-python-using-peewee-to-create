2. Retrieve all stores and in python loop through them and print out their names

   `>>> query = Store.select()`  
   `>>> for store in query:`  
   `... print(store.name)`  
   `...`  
   `Meng's Camera Store`  
   `Store 2`  
   `Store 3`  
   `Store 4`

3. Retrieve only the FIRST store

   `>>> query = Store.select()`  
   `... .where(Store.id==1)`

   `>>> for store in query:`  
   `... print(store.name)`  
   `...`  
   `Meng's Camera Store`

4. Retrieve a store by the name of the store e.g. "Store 3"

   `>>> query = Store.select()`  
   `... .where(Store.name=='Store 3')`

5. Retrieve a store by id

   `>>> query = Store.select()`  
   `... .where(Store.id==3)`

6. Retrieve all the warehouses for the \*store you created in the previous lesson (use join)

   `>>> query = (Warehouse`  
   `... .select(Warehouse, Store)`  
   `... .join(Store)`  
   `... .where(Store.id==1))`

   `>>> for warehouse in query:`  
    `... print(warehouse.location)`  
    `...`  
    `Damansara Warehouse`  
    `Port Klang Warehouse`

7. Retrieve all the products for the \*store you created in the previous lesson (use join)

   `>>> query = (Product`  
   `... .select(Product)`  
   `... .join(Warehouse)`  
   `... .switch(Warehouse)`  
   `... .join(Store)`  
   `... .where(Store.id==1))`

   `>>> for product in query:`  
   `>>> ... print(product.name)`  
   `>>> ... print(product.description)`  
   `>>> ...`  
   `>>> MacBook Pro`  
   `>>> Expensive computer`

8. For the only product in your database, retrieve the warehouse it belongs to (use join)

   `>>> q = (Warehouse.select()`  
   `... .join(Product)`  
   `... .where(Product.id == 1))`

   `>>> for wh in q:`  
   `>>> ... print(wh.location)`  
    `>>> ...`  
   `>>> Damansara Warehouse`

9. For the only product in your database, retrieve which store it belongs to (use join)

   `>>> q = Store.select()`  
   `.join(Warehouse)`  
   `.join(Product)`  
   `.where(Product.id == 1)`  
   `>>> for store in q:`  
   `... print(store.name)`  
   `...`  
   `Meng's Camera Store`
