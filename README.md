# Ashe eCommerce 

This project will be a fully functional eCommerece website with user and guest checkout capabilities. We will start first by setting up our templates and data structure in the first two modules, then moving on to adding user checkout flow with payment integration.

After we complete basic checkout with a logged in user, we will add in the ability for users to checkout as a guest using cookies.

-- Made for CS50’s Web Programming with Python and JavaScript course as its graduation project.

## What is it ?  

This project will be a fully functional Gaming skins store with user and guest checkout capabilities. We will start first by setting up our templates and data structure in the first two modules, then moving on to adding user checkout flow with payment integration.

After we complete basic checkout with a logged in user, we will add in the ability for users to checkout as a guest using cookies.
![Store View](https://i.ibb.co/j3fcxtX/store.png)


### Payment Integration

![Store View](https://i.ibb.co/KDcC2VG/checkout.png)

Payment integration will be handled with PayPal offering the ability to checkout with a PayPal account and checkout with PayPal debit/credit card. Stripe integration is simple to add but for the purpose of international transactions we will focus on PayPal for international availability and security.

![Store View](https://i.ibb.co/p4BLpMG/store.png
)

### User/Guest Checkout

The main focus of this eCommerce project will be to integrate guest checkout ability along with user accounts. Many eCommerce tutorials/demo’s have one or the other but I could not find any at this time that contain both.

```Quote
“A good eCommerce website should always give the user the ability to checkout without creating an account.“ 
```

This kind of functionality has come to be expected by users and forcing them to create an account can affect sales significantly as any resistance does.

### Authenticated User Vs Guest Checkout

Authenticated users & guests have virtually the same process with slight differences. Users with accounts will have the ability to view pending and previous orders while guests will have items stored in cookies and will have the option to create account after a successful purchase.

#### Authenticated User Process

Add item to cart → Edit Order → Checkout
View pending and previous orders + Order details 

#### Guest Checkout Process

Add item to cart → Edit Order → Checkout
Create Account to view Order

### Models

![Store View](https://stepswithcode.s3.us-west-2.amazonaws.com/introduction/models.png)

This project will consist of 6 Models, so let's summarize each one:

1. USER - Built in Django user model,  instance created for each customer who registers.

2. CUSTOMER - Along with a User model, each customer will contain a Customer model that holds a one to one relationship to each user. (OneToOneFied)

3. PRODUCT - The product model represents product types we have in store.

4. ORDER - The order model will represent a transaction that is placed or pending. The model will hold information such as the transaction ID, data completed and order status. This model will be a child or the customer model but a parent to Order Items.

5. ORDERITEM - An order Item is one item with an order. For example, a shopping cart may consist of many items but is all part of one order. Therfore the OrderItem model will be a child of the PRODUCT model AND the ORDER Model.

6. SHIPPING - Not every order will need shipping information. For orders containing physical products that need to be shipping we will need to create an instance of the shipping model to know where to send the order. Shipping will simply be a child of the order model when necessary.