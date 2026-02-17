# Project-Specific Questions

## Project 1: FashionHub (E-commerce Website)

**Tech Stack**: HTML, CSS, JavaScript, EJS, Express, Node.js

### Q1: Can you explain the architecture of your FashionHub project?

**Answer**:
"FashionHub follows the MVC (Model-View-Controller) architecture.

- **Model**: I used MongoDB schemas to define the structure for Users and Products.
- **View**: EJS (Embedded JavaScript) was used for server-side rendering of dynamic HTML pages.
- **Controller**: Express.js handled the routing and business logic, processing user requests and interacting with the database."

### Q2: How did you implement the "Category Handling" feature?

**Answer**:
"I created a database schema specifically for categories. In the frontend, I used dynamic routing in Express. When a user clicks a category, the server fetches only products matching that category ID from MongoDB and renders the product listing page. This reduces load time compared to filtering on the client side."

### Q3: You mentioned improving buying process efficiency by 35%. How did you measure that?

**Answer**:
"I streamlined the checkout flow. Originally, it required 5 steps. I optimized it to a 3-step process (Cart -> Address/Payment -> Confirmation) and implemented local storage to persist cart data so users wouldn't lose items on refresh. User testing showed a significant reduction in time-to-purchase."

---

## Project 2: Bike & Scooter Rental System

**Tech Stack**: React.js, Node.js, Express.js, MongoDB

### Q1: Why did you choose React for this project over EJS (which you used in FashionHub)?

**Answer**:
"I chose React because the Rental System required a highly interactive, single-page application (SPA) experience. Features like real-time availability checking and dynamic pricing calculations needed immediate UI updates without reloading the page, which React's Virtual DOM handles efficiently."

### Q2: How did you handle "Real-time tracking"?

**Answer**:
*(If you used a specific library, mention it. If it was a mock implementation, be honest but technical)*
"For the prototype, I integrated the **Google Maps API** (or Leaflet.js). The frontend periodically fetches the vehicle's mock GPS coordinates from the backend via a REST API endpoint every few seconds to update the marker position on the map, simulating real-time movement."

### Q3: How do you handle secure transactions in your application?

**Answer**:
"I integrated a payment gateway (like Razorpay or Stripe). Crucially, I ensured that no sensitive card details are stored in my database. My backend only handles the order creation and verifying the transaction signature returned by the payment provider to ensure authenticity."

---

## General Project Questions

### Q: What was the most challenging bug you faced?

**Answer**:
"In the Rental System, I faced an issue where double-bookings were happening for the same bike. I solved this by implementing database transactions (or using optimistic locking) in MongoDB to ensure that once a vehicle is reserved, it is immediately marked as 'unavailable' before the payment process completes."
