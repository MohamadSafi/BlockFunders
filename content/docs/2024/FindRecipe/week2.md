---
title: "Week #2"
---

# **Week #2**

## **Week 2 - Choosing the Tech Stack, Designing the Architecture**

### **Tech Stack Selection**

* Backend framework: FastAPI was chosen for its reliability and efficiency in backend development, allowing for quick API creation in Python.

* Bot development: We chose telebot, a Python library designed for bot development, to take advantage of our team's Python knowledge and make bot development easier.

* Database: MongoDB was chosen because of its reliability and compatibility with Python, allowing for easy data management and scalability as required by our project.

* Programming Language: Python is preferred by all because to the significant experience and skill of all team members, resulting in smooth development and maintenance.

* Containerization: Docker is used to increase deployment flexibility and consistency across multiple environments, ensuring that our program scales and is managed efficiently.


### **Architecture Design**

1. **Component Breakdown**:

![project_schema](/2024/FindRecipe/project_schema.jpg)

* Telegram bot: A Telegram bot acts as the primary interface for communicating with clients, allowing them to interact with the server and obtain information. It is in charge of receiving user requests, routing them to the server for processing, and returning results to users. 

* Server: The server functions as a computational engine, calculating and optimizing menu composition based on incoming requests. It communicates with the database to retrieve recipe information, processes Telegram bot requests, and creates ideal menu suggestions, effectively centralizing the system's main operation.

* Database: The database contains and manages the recipe information necessary for menu design. It communicates with the server to deliver data updates and receive recipe information as needed.


2. **Data Management**: 

* MongoDB is chosen for data storage and management due to its fast, flexible, scalable, and Python-integrated capabilities. The server will access and manipulate data using MongoDB drivers and libraries, ensuring efficient processing and data integrity. The diagram depicts the MongoDB schema, outlining the structure and relationships of stored data for efficient menu generation and recipe management.
![database](/2024/FindRecipe/DataBase.png)


3. **User Interface (UI) Design**:

The following image demonstrates the preliminary design of a Telegram Bot, showcasing its user interface. The picture shows only possible style of the bot and not demonstrating the final variant.
![bot_visual](/2024/FindRecipe/Visual.jpg)

The bot logic will be based on the following diagram
![bot_UI_diagram](/2024/FindRecipe/BotUI.jpg)

4. **Integration and APIs**: 

Our application's API has a "create" method that allows to generate menus depending on specific parameters. This method supports parameters such as calories, cooking time, recipe difficulty, spiciness degree, and amount of ingredients/products. These options are used to dynamically construct a menu based on the user's preferences, and the method returns the generated menu. The data is formatted  as JSON objects, making them easy to use.

Structure of request for our server:

![request_struct](/2024/FindRecipe/API_req.jpg)

Structure of response from our server:

![response_struct](/2024/FindRecipe/API_res.jpg)

5. **Scalability and Performance**: 

We built the server using FastAPI, a technology known for its multiple benefits. One of its primary characteristics is its support for asynchronous processing, which allows it to handle multiple clients at the same time, increasing scalability significantly. FastAPI is also known for its great performance in the market, ensuring that our server can easily manage current architecture while also supporting future development.

Our architecture's design enables for the addition of new functionalities at any stage, demonstrating the system's inherent flexibility. Each component runs independently, ensuring that scalability is maintained across all nodes with no interdependencies, allowing the system to handle increased user loads and data volumes without sacrificing speed.

6. **Security and Privacy**: 

As our application operates on Telegram, we don't offer standard registration processes, passwords, or other authentication methods. Furthermore, we don't collect any personal user data, which reduces the need for extensive encryption and strong database security against data leakage. Users communicate with our Telegram bot using predefined buttons, which minimizes the danger of SQL injection attacks and reduces the need for further input validation.

However, we focus security by increasing fault tolerance to reduce potential risks like DoS/DDoS attacks. To protect against this, we want to establish a rate-limiting policy that limits the amount of queries a user may make in a given interval. To avoid service disruptions, our system will temporarily ban a single user if they make too many requests. Once the blocking time expires, the user will be unblocked, ensuring continued service availability and resilience against malicious activities.

7. **Error Handling and Resilience**: 

To ensure a reliable application, we are planning to build comprehensive strategies for error handling and exception management. Our approach includes the implementation of  error logging and monitoring systems to detect and analyze issues in real-time. By using try/catch blocks and raising exceptions appropriately, we aim to manage unexpected errors gracefully, minimizing their impact on the user experience.

Furthermore, we plan to enhance the robustness of our service by covering our code with unit tests. This measure will help us identify and address potential issues early in the development cycle, ensuring the stability of our application. 

8. **Deployment and DevOps**: 

We will leverage Docker to containerize all components of our product, creating consistent and isolated environments for each service. Dockerfiles will be written for each component to automate the building and deployment processes, ensuring reproducibility and ease of scaling.

For deployment, we will use an online service to host and manage our containers, providing greater stability and reliability.  For robust development workflow we are thinking of building CI/CD pipelines to automate testing, building, and deployment tasks.

### **Week 2 questionnaire:**

1) Tech Stack Resources: 

We do not use any project-based books as source of technical information. 
Instead we utilize internet resources

2) Mentorship Support: 

Currently, we do not have a mentor actively involved in our project, nor have we sought one. 
However, we may consider seeking mentorship in the future for guidance and support, especially in addressing specific project-related queries and challenges.

3) Exploring Alternative Resources: 

As a main source of information within out tech stack we use technical documentation of the tools we use. 
If specific questions appear we seek for help  in video tutorials and blogs. (stackoverflow, geeksforgeeks, FastAPI course (https://www.youtube.com/playlist?list=PLeLN0qH0-mCVQKZ8-W1LhxDcVlWtTALCS))

4) Identifying Knowledge Gaps: 

There are indeed knowledge gaps within our tech stack that we aim to address. 
We plan to fill these gaps through the use of video tutorials, detailed documentation reviews, and by actively seeking clarification through inquiries.

5) Engaging with the Tech Community: 

We actively engage with the tech community of our unversity (coursemates, professors). 
These engagements allow us to seek guidance and learn from professionals in our tech stack.

6) Learning Objectives: 

This week, our specific learning objectives include deepening our understanding of advanced features within our tech stack and understanding what specifically is needed for our project. 
To achieve these objectives, we will utilize video tutorials, participate in focused discussions, and explore advanced technical documentation.

7) Sharing Knowledge with Peers: 

We facilitate the exchange of insights and experiences related to our tech stack through organized knowledge-sharing sessions and discussions among team members. 
Moreover, whenever some of us has a technical related question, we seek for help in our team's chat where everyone is ready to help.

8) Leveraging AI: 

We leverage LLMs if there are specific issues or to structure our knowledge.

### **Tech Stack and Team Allocation**

| Team Member        | Track               | Responsibilities  |
|--------------------|---------------------|-------------------|
| Egor Lebedev       | Backend             | Server on FastAPI |
| Alie Ablaeva       | Backend/UI/Design   | Telegram Bot      |
| Sofia Gamershmidt  | Backend/UI/Design   | Telegram Bot      |
| Ilsiia Nasibullina | Backend/UI/DB       | Telegram Bot      |  
| Alex Shulmin       | Backend/DB          | MongoDB, Parsing  |

### **Weekly Progress Report**

This week our team has been researching available information, recipes.
We started parsing the food.ru website and converting the information into a database.

### **Challenges & Solutions**

The parsing issue was identified as stemming from query limitations and user bans in the food.ru, significantly affecting our operations. Through diligent troubleshooting, we successfully resolved the issue by implementing carefully selected optimal timeouts. This solution has effectively restored functionality and improved the stability of our parsing system, ensuring smoother and more reliable performance moving forward.
Now, we have a comprehensive dataset of recipes at our disposal.


### **Conclusions & Next Steps**

Now that we have a database in place, we're ready to proceed with server development. While the database can be expanded over time, its current state allows us to initiate the next phase of our project. Our immediate priority is to securely host the database on a remote resource to enable seamless access and integration into our server infrastructure. This step is crucial for facilitating efficient data management and ensuring our development efforts progress smoothly. With the database securely accessible remotely, we can begin laying the foundation for robust server functionalities and further advancements in our project goals.
