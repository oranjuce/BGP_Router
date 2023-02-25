Project 3: BGP Router

This program is a simple implementation of a routing protocol for an autonomous system, represented by a single router. The router is implemented as a class, and its main functionality is to handle incoming and outgoing messages, update its forwarding table, and send updates to neighboring routers. The program reads a JSON file containing the configuration of the router and its neighbors, which includes the ports on which to listen for incoming messages, the type of relationship (e.g., customer, peer, provider), and the IP addresses of its neighbors.

The router class has several instance variables, including the forwarding table, disaggregated forwarding table, sockets, and ports, which are initialized in the constructor. The forwarding table is used to store information about how to forward packets to other routers, while the disaggregated forwarding table stores the same information in a more detailed form. The sockets and ports are used to listen for incoming messages from neighbors.

The program provides several methods that are used by the router to handle incoming and outgoing messages. The data() method is used to send a message to the appropriate destination, based on the router's forwarding table. If the router cannot find a route to the destination, it sends a "no route" message back to the source. The get_routes() method is used to find the appropriate routes for a given message, based on the forwarding table of the node. The reduce_routes() method is used to filter routes to only the best route for each neighbor. The update() method is used to update the router's forwarding table based on the updates received from its neighbors.

The program also includes a main method that reads the configuration file, creates a router object for each AS, and runs the routers. The program continuously listens for incoming messages on each router's port, and dispatches them to the appropriate router object.

Challenging aspects of this program were understanding how to coalese and aggregate for the final stages of tests, as well as maintainng a readable code design.

