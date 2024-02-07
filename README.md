# TechnoCommerce

### <b>TechnoCommerce is an E-Commerce site with 3 APIs: E-Commerce API, Bank API, and Supplier API</b>

<br/>

## Motivation

E-Commerce can save time for both the buyer and supplier, reducing phone calls about availability, specifications, hours of operation, or other information easily found on company and product pages.

## Features Implemented

- <b> A Responsive UI for users </b>
- <b> User </b>
  - Authentication
    - Login, Register, Logout
    - Change Password
  - Profile
    - Update Profile
    - Can see his/her order's list
- <b> Product </b>
  - Product of different categories
  - User can review a product
  - Based on the user review, a rating is calculated
  - Search Product
  - Every user can see reviews of a product
- <b> Cart </b>
  - Add product to cart
  - Quantity Select
  - Remove the product from the cart
- <b> Checkout Order </b>
  - Select the shipping address
  - Payment Method [ Bank API ]
  - User can see order summary when placing order
- <b> Order Payment </b>
  - Pay using the selected payment method
  - E-commerce asks for a secret PIN to verify the transaction
  - An invoice pdf is generated after payment
  - User can view or download the invoice
- <b> Admin </b>
  - Manage User
    - Can see user list
    - Can make a user admin
    - Delete user if he/she violates TechnoCommerce policy
  - Manage Product
    - Can see product list
    - Can create the product by giving a product description
    - Can upload product image
    - Can update product details
    - Can manage inventory
    - Delete product
  - Manage Order
    - Can see the order list
    - Can see if the user payment is completed or not for a particular order
    - Can see if a particular order is delivered or not
    - Can see order details
    - See the payment details
    - Can pay the supplier through bank API and get transaction ID as a response
    - Can send order requests with transaction ID and ordered products to the supplier through the supplier API. Supplier API verifies the transaction delivers the product and sends the delivery response to the admin and the admin marks the order as delivered.
- <b> E-Commerce API </b>
  - User Routes
    - Authentication
    - Register user
    - Get an authenticated profile
    - Update user profile
    - Get all users
    - Get user by ID
    - Delete users
  - Product Routes
    - Get all products
    - Get product by id
    - Delete product
    - Update product
    - Create a product review
  - Order Routes
    - Create Order
    - Get order by ID
    - Get all orders
    - Get authenticated user's orders
    - Change the payment status of an order
    - Change supplier payment status
    - Change delivery status
- <b>Supplier API</b>
  - User Routes
    - Authentication
    - Register user
    - Get all users
    - Get user by ID
    - Get users by bank account
  - Delivery Request Route
    - Handle delivery
- <b>Bank API</b>
  - User Routes
    - Authentication
    - Register user
    - Get all users
    - Get user balance
    - Deposit balance
  - Payment Routes
    - Pay money
    - Is payment possible
  - Transaction Routes
    - Get all transaction
    - Get transaction by ID
    - Verify transaction

## Work Flow

The user registers on the website with personal details and bank information. Users can see all the products on the home screen and add chosen products to the cart. Users can place an order and the order summary is visible to the user. The User has to pay for the order.<br>
The user pays the required amount to the E-Commerce through the bank API. Then bank API returns the transaction number. After that an invoice is generated with the order details and the user can view or download the invoice.<br>
E-Commerce pays the supplier through the bank API and bank API returns a transaction number. E-Commerce then sends a delivery request to the supplier API with the transaction number and ordered products.
<br>
The supplier verifies the transaction through the bank API. If the transaction is verified, the supplier delivers the product to the user and sends the delivery status to the E-Commerce.

## Used Technologies

- Language: JavaScript
- Frontend: React, Redux, HTML, CSS
- Backend: Node.js, Express.js
- Database: MongoDB

## Clone this Project

```
git clone https://github.com/rrupom/techno-commerce.git
```

## Run the Project in your Machine

Install Backend Dependencies:

```
npm i
```

Install Frontend Dependecies:

```
cd frontend
npm i
cd ..
cd bankfrontend
npm i
cd ..
```

To Run The Project

```
npm run dev
```

Rename the file named ".env.example" as ".env". Edit the file and assign PORT, PORT_BANK, PORT_SUPPLIER, MONGO_URI, MONGO_URI_BANK, PORT_SUPPLIER, JWT_SECRET according to instructions written in this file.  
<br>
