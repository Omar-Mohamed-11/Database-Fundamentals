- How to set up databases in different centralized environments?

1. **Mainframe environment:** 
	- A single mainframe computer hosts both the database and application servers.
	- Users connect via dummy terminals that do no processing themselves, the processing depends on one server.
	  This setup is slow, has a single point of failure, and high traffic causing delays.
	- **Disadvantages:**
		- The processing depends on one server.
		- The performance is very low.
		- Database and application layer has *Single Point of failure*.

2. **Client/Server environment:**
	- A two-tier model with a database server and clients that have the application installed locally (*Thick Clients*).
	- This improves performance but still has a single point of failure at the database server and high maintenance costs due to application updates on each client.
	- **Disadvantages:**
		- Database is a single point of failure.
		- High cost for support.
	- **Advantages:**
		- Application layer is not a single point of failure.

3. **Internet Computing environment (Three-Tier Architecture):**
	- Consists of a database server, an application server (middle tier), and thin clients that access the application via a browser or small app. This reduces maintenance costs, supports load balancing with multiple application servers, and improves resilience. However, the database server remains a single point of failure.
	- **Disadvantages:**
		- Application server is a single point of failure.
		- Database is a single point of failure.
	- **Advantages:**
		- Lower cost for support and maintenance.

	- **N-Tier Architecture:**
		- We can put many *Application Servers* in the middle tier.
		  In this architecture, the system is divided into three layers:
			1. Database Storage (Database Server): This is where all the data is stored and managed.
			2. Middle Tier (Application Server): This layer hosts the application logic. It processes user requests, runs the application, and communicates between the client and the database server.
			3. Client (Thin Client): The client runs a small application, often a web-based interface accessed through a browser or a lightweight applet. This is called a "thin client" because it does minimal processing locally.

	- While the three-tier model improves many issues, the centralized database server remains a critical vulnerability, and recovery after failure can be time-consuming.