# MongoDB Day 1 Task

## Product JSON
The data for the products can be found at the following URL: [Product JSON](https://github.com/rvsp/database/blob/master/mongodb/product.json).

## 📋 Task Description

Write the corresponding MongoDB queries for the following questions:

1. **Find all the information about each product**
2. **Find the product prices which are between 400 to 800**
3. **Find the product prices which are not between 400 to 600**
4. **List the four products which are greater than 500 in price**
5. **Find the product name and product material of each product**
6. **Find the product with a row id of 10**
7. **Find only the product name and product material**
8. **Find all products which contain the value of "soft" in product material**
9. **Find products which contain product color "indigo" and product price 492.00**
10. **Delete the products which have a product price value of 28**

## 🛠️ MongoDB Queries

1. **Find all the information about each product**

     db.products.find();

2. **Find the product prices which are between 400 to 800**

      db.products.find({product_price:{$gte:400,$lte:800}});

3. **Find the product prices which are not between 400 to 600**

       db.products.find({$or:[{product_price:{$gt:600}},{product_price:{$lt:400}}]});

4. **List the four products which are greater than 500 in price**

      db.products.find({ product_price: { $gt: 500 } }).limit(4);
   
5. **Find the product name and product material of each product**

      db.products.find().forEach((pro) => {
        print("Product Name: " + pro.product_name);
        print("Product Material: " + pro.product_material);
      });

6. **Find the product with a row id of 10**

     db.products.find({id:"10"});

7. **Find only the product name and product material**

   db.products.find().forEach((pro) => {
      print("Product Name: " + pro.product_name);
      print("Product Material: " + pro.product_material);
    });

8. **Find all products which contain the value of "soft" in product material**

    db.products.find({product_material:'Soft'});

9. **Find products which contain product color "indigo" and product price 492.00**

    db.products.find({product_material:'Soft'});

10. **Delete the products which have a product price value of 28**

    db.products.deleteMany({ product_price: 28 });
   



