# E-Commerce-API

### If you want to look first er diagram for build this databases used:
https://drive.google.com/file/d/1gBLTPrtSUoiNgWHsW7hfFgIheSGbCjlj/view?usp=sharing

### How to run:
```
npm run start
```

## user
### post user/sign-up
request body:
```json
{
    name:"arr",
    email:"arr@gmail.com"
    password:"*****"
}
```

response success:
```json
{
    message:"register success"
    user:"arr"
    }
```
response failure:
```json
{
    message:"register failure"
    }
```

### post user/sign-in
request body:
```json
{
    "name":"arr or email",
    "password":"*****"
}
```

response success:
```json
headers: token

{
    message:"login success"
    userId:1
}
```

response failure:
```json
{
    message:"sign-in failed"
}
```

## product
### get product/list
request headers: token

response success:
```json
{
    products: [
        {
            id: 1,
            name: "product1",
            price:12000,
            stock:100,
            size: "XL",
            category:"shirt"
        },
         {
            id: 2,
            name: "product1",
            price:12000,
            stock:100,
            size: "XL",
            category:"shirt"
        },
         {
            id: 3,
            name: "product1",
            price:12000,
            stock:100,
            size: "XL",
            category:"shirt"
        }
    ]
}
```
response failure:
```json
{
    message: "failed to get product list"
}
```

### get product/:id
request headers: token

response success:
```json
         {
            id: 1,
            name: "product1",
            price:12000,
            stock:100,
            size: "XL",
            category:"shirt"
        }
```
response failure:
```json
{
    message:"product not available"
}

```
### get product/search?name={name=keyword}&category={category}
request headers: token

response success:
```json
{
    products: [
        {
            id: 1,
            name: "product1",
            price:12000,
            stock:100,
            size: "XL",
            category:"shirt"
        },
         {
            id: 2,
            name: "product1",
            price:12000,
            stock:100,
            size: "XL",
            category:"shirt"
        },
         {
            id: 3,
            name: "product1",
            price:12000,
            stock:100,
            size: "XL",
            category:"shirt"
        }
    ]
}
```
response failure:
```json
{
    message: "failed to get product list"
}
```

### post product/shopping-cart
request headers: token
request body:
```json
{
    productId:1,
    userId:1,
    quantity:2
}
```

response success:
```json
{
    "message": "product added to cart successfully",
    cartId:1
}
```
response failure:
```json
{
    "message": "failed add to cart",
}
```

### delete product/shopping-cart/:cartId
request headers: token
response success:
```json
{
    message: "ok"
}
```
response failure:
```json
{
    message:"not found"
}
```

### post product/checkout
request header:token

request body:
```json
{
    userId:1,
    createdAt: "DD/MM/YYYY 12:00",
    totalAmount:20000
}
```