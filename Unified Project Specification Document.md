---

# **Saaree Store Website – Product Requirement Document (PRD)**

**Project Name:** SwiftCart – Modern Ecommerce Platform for India
**Prepared By:** \[Your Name]
**Date:** 10 Aug 2025

---

## **1. Project Overview**

SwiftCart is a modern ecommerce platform tailored for the Indian market. It will enable customers to browse products, apply discounts, post reviews, and purchase items securely using UPI and card-based payment methods. The platform will be responsive, scalable, and integrated with a CMS (Strapi) for easy content management.

**Goals:**

* Offer a seamless online shopping experience.
* Support up to 10,000 users in the first year.
* Implement secure payments with Razorpay.
* Enable easy management of products, categories, and discounts from the backend.

---

## **2. Target Audience**

* Indian consumers seeking online shopping.
* Small to medium-sized retailers looking to sell products online.

---

## **3. Key Features**

### **3.1 MVP Features**

* **Authentication** → Clerk.js-based login/signup.
* **Product Browsing** → By category, with search & filters.
* **Shopping Cart** → Add/update/remove products.
* **Discount System** → Apply coupon codes.
* **Checkout** → Integrated Razorpay payments.
* **Order History** → For logged-in users.
* **Review System** → Users can leave ratings & comments.
* **Admin Panel** → Manage products, categories, discounts, orders, reviews.

### **3.2 Future Scope**

* Wishlist feature.
* Seller dashboard.
* Live chat support.
* AI-based recommendations.

---

## **4. Functional Requirements**

### **4.1 User Roles**

* **Guest** → Browse products, view reviews.
* **Registered User** → All guest features + cart, checkout, reviews, order history.
* **Admin** → Manage all content and orders.

### **4.2 Example Flow – Checkout**

1. User logs in via Clerk.js.
2. Adds products to cart.
3. Proceeds to checkout page.
4. Fills in shipping address.
5. Applies discount code (optional).
6. Pays via Razorpay.
7. Order is saved in Strapi database.
8. User receives email confirmation.

---

## **5. Technical Specifications**

**Frontend:**

* React (Vite) + TailwindCSS + TypeScript
* Clerk.js for authentication

**Backend:**

* Strapi CMS (Node.js)
* SQLite (development), PostgreSQL (production)

**Payments:**

* Razorpay API (UPI, cards, net banking)

**Architecture:**

```
React (Frontend) → Clerk.js (Auth) → Strapi (Backend) → PostgreSQL (DB)
                                           ↓
                                        Razorpay (Payment)
```

---

## **6. Database Structure (Strapi Collections)**

1. **Product** → title, description, price, stock, images, category, reviews
2. **Category** → name, description
3. **Discount** → code, percentage, expiry date, applicable products/categories
4. **Order** → user, products, total, status, shipping address, paymentId
5. **Review** → user, product, rating, comment, date

---

## **7. API Endpoints**

**Product APIs**

* `GET /products` → List all products
* `GET /products/:id` → Product details

**Order APIs**

* `POST /orders` → Create new order
* `GET /orders` → List user’s orders

**Discount APIs**

* `POST /discounts/apply` → Validate and apply discount code

**Review APIs**

* `POST /reviews` → Add review
* `GET /reviews/:productId` → Get reviews for a product

---

## **8. Wireframes (Text Version)**

**Home Page:**
\[Header: Logo | Search | Cart | Login]
\[Banner Image]
\[Categories List]
\[Products Grid]

**Product Page:**
\[Product Image] | \[Title | Price | Add to Cart]
\[Description]
\[Reviews Section]

**Checkout Page:**
\[Cart Items]
\[Address Form]
\[Discount Code Input]
\[Payment Button]

---

## **9. Success Metrics**

* Achieve 5,000+ orders in first 6 months.
* Maintain >80% customer satisfaction rating.
* 90% of orders completed without payment issues.

---
