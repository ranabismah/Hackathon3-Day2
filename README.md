# hackathon3-day2
#1. Frontend (Next.js)
Objective:
Create a responsive and user-friendly interface for browsing furniture products.

Tasks:

Essential Pages:

Home: Display featured products, categories, and promotions.
Product Listing: Show products filtered by categories like Living Room, Bedroom, etc.
Product Details: Provide detailed information about selected products.
Cart: Allow users to review and modify selected items.
Checkout: Collect customer details and payment information.
Order Confirmation: Display order details and a confirmation message.
Key Features:

Fetch data from the backend (Sanity CMS) using APIs via GROQ (GraphQL) queries.
Implement dynamic routing for pages like /products/:id.
#2. Backend (Sanity CMS)
Objective:
Act as the content management system for managing all data related to products, orders, and customer interactions.

Tasks:

Schema Design:

Products: Fields include name, price, stock, image, category, description.
Categories: Fields include name, description, and associated products.
Orders: Fields include customer details, product IDs, quantities, payment status, and order status.
Key Features:

Use Sanity's real-time data management to provide dynamic updates to the frontend.
Efficiently store and retrieve data for frontend interactions.
#3. Interaction Between Frontend and Backend
Fetching Data:

The frontend (Next.js) sends API requests to Sanity to retrieve product and category information using GROQ queries.
Example GROQ Query:

*[_type == "product"] {
  _id,
  name,
  price,
  category->name,
  images
}
Submitting Orders:

When a user places an order, the frontend sends a POST request to the backend (Sanity CMS) to store the order details.
Sanity manages and tracks order data, including customer information, purchased products, and order status.
4. API Requirements
Objective: Define clear and efficient endpoints for seamless interaction between frontend and backend.

#Endpoints:

/products:
Method: GET
Purpose: Fetch all available products from Sanity.
Response: Product details (ID, name, price, stock, image).

/categories:
Method: GET
Purpose: Fetch all product categories.
Response: Category details (ID, name, description).

/orders:
Method: POST
Purpose: Submit a new order.
Payload: Customer info, product details, and payment status.

/shipment:
Method: GET
Purpose: Track order shipment status via a third-party API.
Response: Shipment ID, order ID, status, and expected delivery date.
5. System Architecture
Objective: Visualize the interaction between system components.

