# MongoDB Task - Queries on Product JSON

Below are the specific tasks and it's queries

1. **Find all the information about each products**:
    ```javascript
    db.products.find({})
    ```

2. **Find the product price which are between 400 to 800**:
    ```javascript
    db.products.find({ product_price: { $gte: 400, $lte: 800 } })
    ```

3. **Find the product price which are not between 400 to 600**:
    ```javascript
    db.products.find({
        $or: [
            { product_price: { $lt: 400 } },
            { product_price: { $gt: 600 } }
        ]
    })
    ```

4. **List the four product which are greater than 500 in price**:
    ```javascript
    db.products.find({ product_price: { $gt: 500 } }).limit(4)
    ```

5. **Find the product name and product material of each products**:
    ```javascript
    db.products.find({}, { product_name: 1, product_material: 1})
    ```

6. **Find the product with a row id of 10**:
    ```javascript
    db.products.find({ id: "10" })
    ```

7. **Find only the product name and product material**:
    ```javascript
    db.products.find({}, { product_name: 1, product_material: 1, _id: 0 })
    ```

8. **Find all products which contain the value of soft in product material**:
    ```javascript
    db.products.find({ product_material: "Soft" })
    ```

9. **Find products which contain product color indigo and product price 492.00**:
    ```javascript
    db.products.find({
    $or: [
        { product_color: "indigo" },
        { product_price: 492.00 }
    ]})

    ```

10. **Delete the products which product price value are 28**:
    ```javascript
    db.products.deleteMany({ product_price: 28 })
    ```
