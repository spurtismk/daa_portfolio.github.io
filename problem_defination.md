 # **Introduction**
 
The selected project focuses on the design and development of a restaurant management system, a crucial domain in the hospitality industry. A restaurant management system integrates various aspects of restaurant operations, including order management, inventory tracking, billing, and customer service. Efficient management of these areas is essential for ensuring smooth restaurant operations and improving customer satisfaction.
The project was selected after reviewing a relevant white paper on modern restaurant management systems, which explored the challenges and solutions in automating and optimizing restaurant processes. The white paper discussed the increasing demand for digital solutions in the restaurant industry and how software systems can streamline tasks such as order taking, kitchen management, and payment processing. Drawing inspiration from the findings in the paper, the project aims to design a system that enhances operational efficiency, reduces human error, and provides an improved customer experience through features such as real-time order tracking and automated billing. The system also aims to address inventory management challenges by integrating real-time data to track stock levels and order supplies. This project serves as an essential step in understanding the role of technology in the restaurant industry and contributes to ongoing research in developing smarter, more efficient solutions for hospitality businesses.

References: [1] White Paper on Modern Restaurant Management Systems.

#  **Problem Statement**

# Domain
The problem being addressed in this project is the inefficiency and manual errors that occur in traditional restaurant management. Restaurants often struggle with order tracking, inventory management, and billing, leading to delays, inaccuracies, and poor customer experiences. This project aims to automate these processes through a comprehensive restaurant management system that integrates order management, real-time inventory tracking, and automated billing, improving operational efficiency.

The need for this system was identified from a white paper on modern restaurant management systems, which emphasized the challenges faced by restaurants in managing high-volume operations manually. The paper highlighted how automation can reduce human error, speed up service, and enhance customer satisfaction. Motivated by the need to improve restaurant operations, the project was selected to provide a solution that streamlines daily tasks, allowing restaurant staff to focus on quality service while minimizing errors and inefficiencies.


# Module Description
In this project, the focus is on developing and automating the Order Management and Billing System modules for the restaurant management system.
The Order Management module is designed to streamline the process of taking, tracking, and processing customer orders. It allows waitstaff to input orders into the system, which are then transmitted directly to the kitchen for preparation. This minimizes the chances of manual errors, reduces the time taken for orders to be relayed, and ensures that kitchen staff have real-time access to customer requests. The module also tracks the status of orders, from being received to being served, and provides timely updates to customers.

The Billing System is integrated with the order management module, ensuring that customers are billed accurately and promptly based on their order history. It automates the process of generating bills, applying discounts, and calculating totals, removing the need for manual calculations and minimizing the risk of billing errors. The system also supports various payment methods, providing flexibility for customers.

By focusing on these modules, the project aims to improve operational efficiency, reduce errors, and enhance customer satisfaction by providing faster and more accurate service. These modules are essential for optimizing the overall restaurant management process.


**Key Features:**
Customer Queue: Allows adding and removing customers from a queue.
Reservations: Allows table reservations and releases them when necessary.
Inventory: Manage stock of items.
Food Menu and Billing: Displays the menu, takes customer orders, and generates bills.
Delivery System: Calculates the shortest distance between locations.
Lodging: Manages available rooms and bookings for customers.
The program is designed to be a management system for a restaurant with functionalities for customer management, inventory management, reservations, food menu, and more.

# **Algorithms Used:**
**Dijkstra's Algorithm (Shortest Path):**

Used in the Delivery System to find the shortest distance between two locations. This algorithm is implemented using a priority queue (min-heap) and works by exploring the closest nodes first. It efficiently finds the shortest path in a weighted graph.

Steps:

Initialize distances to infinity.
Use the priority queue to explore nodes starting from the source.
Update the shortest distance for each adjacent node.
Repeat until all nodes are visited or the destination is found.

void shortestDistance(int source, int destination)
{
    // Dijkstra's algorithm implementation
}

**Depth-First Search (DFS) / Breadth-First Search (BFS) (Graph Traversal):**

Although not directly implemented in the code, these algorithms are commonly used in graph-based systems, such as in the Delivery System, where the graph (locations connected by roads) can be traversed using DFS or BFS for route planning.

**Brute Force search:**

Used in places where specific values need to be found in collections such as reservations, inventory items, and menu items (e.g., checking if a reservation exists for a table or if an item is available in the inventory).
cpp

**Greedy Approach (In the context of room booking):**

The Lodging System uses a simple greedy approach when booking rooms. It books the available room of a particular type and removes it from the set of available rooms.
The selection of a room type is done based on the room type requested, without optimization based on pricing (thus it is a greedy choice, always opting for the first available room).

**Quick Sorting :**

The Set data structure in C++ inherently maintains its elements in sorted order. When rooms are added or released in the Lodging System, they are automatically sorted by their room ID (the first element of the pair). This helps in managing room availability efficiently.

**Priority Que**

If you're calculating the shortest route for a food delivery from the restaurant (source) to a customer’s address (destination), the priority queue helps ensure that you always explore the shortest possible route next, thus optimizing the delivery path.
In summary, the priority queue ensures that the Delivery System always processes the most promising locations (i.e., those with the smallest travel distance) first, making the delivery pathfinding process efficient and optimized for a restaurant delivery system.

**Look up table**

 *1.Lookup in the Hash Table (Menu System)*
 
In the FoodMenu class, you have a hash table (unordered_map<string, double> menu) where the key is the dish name (a string) and the value is the price (a double). The lookup operation in this case is used when taking orders from customers and calculating the total bill.

Role of Lookup:
Retrieve the price of a dish: When a customer places an order, the dish name is provided, and the program looks up the price for that dish in the menu hash table using the dish name as the key.

*2. Lookup in Customer Queue (Customer Management)*

The CustomerQueue class involves managing a queue of customers, but lookup is not directly involved here. However, you can consider the process of displaying customers in the queue as a lookup-like operation.

When you call queue.displayQueue(), it looks through all customers in the queue and displays them. This is a form of iterative lookup, where the program accesses and processes each customer in sequence.

*3. Lookup in Reservations System (Table Reservations)*

The Reservations class uses a map (map<int, pair<string, int>> reservations) where each table number is mapped to a pair containing the customer's name and the number of seats.
