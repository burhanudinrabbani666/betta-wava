# Betta Wava - Adopt Betta

[Betta Wava](https://bettawava.burhanudin.com) is a web application built for betta fish enthusiasts to discover and adopt their favorite fish. Explore a wide range of betta varieties, including Longfin, Plakat, Wild Betta, and Giant. Choose from multiple quality levels such as Competition Grade, Grade A, or even betta fry — perfect for starting your own breeding or farming journey.

## Links

- Website application: https://betta-wava.burhanudin.com
- Restful API: https://betta-wava-api.burhanudin.com

Repository:

- General: https://github.com/burhanudinrabbani666/betta-wava
- Backend: https://github.com/burhanudinrabbani666/betta-wava-api
- Frontend: https://github.com/burhanudinrabbani666/betta-wava-web

Inspiration:

- [Molly Jaya Indonesia](https://mollyjaya.id)
- [Tropicflow](https://tropicflow.com)
- [Uniqlo](https://uniqlo.com)

## Features

- **Home Page**
  - Hero Section
  - Products Catalog
  - Navigation for (much later)
    - Variant
      - Color
      - Grade
- **Product Page**
  - Image URL
  - SKU (Stock keeping Unit)
  - Name
  - Price
  - Description
  - Stock level / In Stock or not
  - Add to Cart Form:
    - Quantity Input
    - Increment and Decrement Button
    - Add to Cart Submit Button
  - Favorites Button (much later)
  - Review other people Aquarium (much later)
  - Treatment Fish Guide (much later)
  - Recomendation for tank (much later)
- **Shopping Cart page**
  - Product items to buy
    - Image, Name, Price, Qunatity, subtotal (Price x Quantity)
    - Remove item
    - Change Quantity form
  - Link: Continue adopt, go to Betta catalogue
  - Link: Checkout
- **Checkout page**
  - Order Summary
    - Input For Discount
    - Product items to buy
    - Grand total of all product items to buy
- **Place Order** / Transaction is being processed

## UI Designs

- Figma: [Betta Wava](https://www.figma.com/design/r4MbE5O51U5mhvq1oljrdO/logo?node-id=32-19&t=KFonU6A3SAQdVi3l-1)

### Home Page

<img src="./images/home-page.jpg" />

### Product Page

<img src="./images/grade-page.png" />

### Shoping cart Page

### Checkout Page

### Place Order

## Backend REST API Endpoints

- Production: `https://github.com/burhanudinrabbani666/betta-wava`
- Local: `http://localhost:3001`

Priority:

| Endpoint              | HTTP  | Description            | Permission |
| --------------------- | ----- | ---------------------- | ---------- |
| `/products`           | `GET` | Get all products       | Public     |
| `/products/{slug}`    | `GET` | Get product by slug    | Public     |
| `/products/{variant}` | `GET` | Get product by Variant | Public     |
| `/products/{color}`   | `GET` | Get product by Color   | Public     |
| `/products/{grade}`   | `GET` | Get product by Grade   | Public     |

With Auth:

| Endpoint         | HTTP   | Description              | Permission    |
| ---------------- | ------ | ------------------------ | ------------- |
| `/users`         | `GET`  | Get all users            | Public        |
| `/users/{id}`    | `GET`  | Get user by id           | Public        |
| `/auth/register` | `POST` | Register new user        | Public        |
| `/auth/login`    | `POST` | Login user               | Public        |
| `/auth/me`       | `GET`  | Check authenticated user | Authenticated |
| `/auth/logout`   | `POST` | Logout user              | Authenticated |

Cart:

| Endpoint           | HTTP     | Description                    | Permission    |
| ------------------ | -------- | ------------------------------ | ------------- |
| `/cart`            | `GET`    | Get user's cart                | Authenticated |
| `/cart/items`      | `PUT`    | Add product & quantity to cart | Authenticated |
| `/cart/items/{id}` | `DELETE` | Delete product from cart       | Authenticated |
| `/cart/items/{id}` | `PATCH`  | Update product quantity        | Authenticated |

## Frontend Pages

Priority:

| Route                | Title                                |
| -------------------- | ------------------------------------ |
| `/`                  | Home Page                            |
| `/products`          | All Products Page                    |
| `/products/:slug`    | One Product by Slug Page             |
| `/products/:variant` | Bettas by Variant in Categories Page |
| `/products/:color`   | Bettas by Color in Categories Page   |
| `/products/:grade`   | Bettas by Grade in Categories Page   |

With Auth:

| Route        | Title                   | Permission    |
| ------------ | ----------------------- | ------------- |
| `/register`  | Register Page           | Public        |
| `/login`     | Login Page              | Public        |
| `/dashboard` | Authenticated User Page | Authenticated |
| `/logout`    | Logout Page             | Authenticated |
| `/cart`      | Cart Page               | Authenticated |

## Data Structure

### Product

```json
{
  "id": "dadw",
  "slug": "betta-halfmoon-multicolor",
  "name": "Betta Halfmoon multicolor",
  "sku": "AZ-BHM-1",
  "price": 50000,
  "stockQuantity": 10,
  "imageUrl": "https://uploadcare.com/images/image.jpg",
  "description": "...",
  "grade": "A",
  "color": "multicolor",
  "variant": "halfmoon",
  "createdAt": "...",
  "updatedAt": "..."
}
```

### Add New Product

Request Body:

```json
{
  "name": "Betta Halfmoon multicolor",
  "sku": "AZ-BHM-1",
  "price": 50000,
  "stockQuantity": 10,
  "imageUrl": "https://uploadcare.com/images/image.jpg",
  "description": "...",
  "grade": "A",
  "color": "multicolor",
  "variant": "halfmoon"
}
```

Response Body:

```json
{
  "id": "dadw",
  "slug": "betta-halfmoon-multicolor",
  "name": "Betta Halfmoon multicolor",
  "sku": "AZ-BHM-1",
  "price": 50000,
  "stockQuantity": 10,
  "imageUrl": "https://uploadcare.com/images/image.jpg",
  "description": "...",
  "grade": "A",
  "color": "multicolor",
  "variant": "halfmoon"
}
```
