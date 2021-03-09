# Ansible
Brief Introduction about Ansible

# NGINX
***
- What is NGINX?

- What is the problem that NGINX is trying to solve?


- NGINX is actually a very smart software and soving the smart problem.

- You worked on a application & you worked on local machine, whenever you run this application at run on a specific port like IDEs development environment.

- Now It's time that you want to put this application  on some big giant servers like AWS, azure etc.

- In that system you have spin of machine ubuntu, centOs and you have install Database on it, deploy your application.

- Next, You spin of you machine probablily npm start or django run 

- Application running on the port 4000

- You ask that hey users please go a head and enjoy my application 

- People are enjoying your application using it every single day, you realize that there are too much traffic on this port.

- Now you either on another instance of this application since they are connected with same database not big issue.

- You want some how that load should be manage.

- So Now you run one more your application which is  another instance of your application on  port 3000 and you emails all your users that port 3000 is also available in case of more traffics

- It sounds great to you but not to your users.

- Again traffic increased exponentially that a there are more ports available 5000, 6000 etc

- This is the classic problem and that's why a software like **NGINX** comes in between

- What NGINX does is that Hey users you probabily aware of already these famous ports like 443 or 80 which is by default your browser  serves so you don't even have to remember these ports.

- Not only that It also put a barrier wall that users doesn't have bother about should I connect this port or that port.

- Behind the scene NGINX actually takes all the requests from the users and wherever these application serving is going to talk to NGINX.

- NGINX smartly manage the load that which server or which instance is having low amount of load and redirect the request on that port.

- If you can use NGINX little bit smartly, you can handle routes. 

- NGINX, actually load up a simple cache that all the requests for this particular  rout store that in a cache so that it doesn;t have to talk with DataBase again and again. And that can serve the request much more faster since It's not taking to the database amd all the entire infrastructure again and again.




## **Ansible**
- Ansible is one of the most popular tool and specially very popular in the community of Devops.
- What ansible is?
- What is the problem that trying to solve?
- Where you can use it?
- Resources

## **Problems that Ansible trying to solve**
***
- Ansible is more popular not only in **Software Engineer Community** but moreover in **Production Engineer Community**.
- There are differents sets of challenges that are handle by the Production Engineer, People who takes your software or a web application and move it on to the Production Environment - **Virtual Machine, AWS, Google Cloud or Azure**
- Ansible is one the most favourite tool for all these production engineers.


## **Ansible**
***
- Ansible is a tool that helps you to either move things in production or the things which are already in the production, there are some config management or there are some updation that needs to be made in the productions.
- It just help you to **Automate** that task.


## **Why Ansible?**
***
- It's not about one machine which is handling your DataBase, FrontEnd, BackEns and everything.

- Usually we prefer to deploy multiple machine either load can be balance in the production or may be some other resaon like separate mail server, separate database server.

- Something that you want to change on all the machine may be there is an version update in the operating system from ubuntu 18 to ubuntu 18.5

- ***There is some updated features that you have launch in your application and your application is running in the different computers to have a load balancing what you are going to do at taht time?***
  - You probabily will use an approach in which you are have a system and you go head and  use **SSH** or any other ways to connect those system
  
  - Logged In each system every single time and perform that update
  
  - It is one of the popular way of doing this way.
  
  - But this is not a feasible approach when you are scaling up 100s of machines.

- Welcome to **Ansible** to solve this problem

- Ansible helps us to actually put a config file and then ansible will automatically be connected to all different machine and will release  those updates whether that **Operating System patching** or **OS Upgrade** or **Configuration Update** or **Update on database** etc Ansible comes between and does that.

> **Ansible is relining on three thigs**
> **Declarative Syntax**
>  **Agentless**
>  **Aware** of what is already there 

#### ***1. Inventory*** is one of the key component How ansible work?
***
- Ansible allows us to have a seperation and as well as segregetion of the servers.
- ```ansible
  mail.example.com
  [webserver]
  foo.example.com
  bar.example.com
  
  [dbserver]
  one.exampl.com
  two.example.com
  three.example.com
  ```

**Ansible allows us to Inventary means categorization & put your servers  into a certain category.**

>  **NOTE : YAML (a recursive acronym for "YAML Ain't Markup Language") is a human-readable data-serialization language.\
   It is commonly used for configuration files and in applications where data is being stored or transmitted.**


>  **Ansible uses ML file, and YML is one of the easiest way of writing the code**
> This is the actual code how you categorized your server code

- ```ansible
  all :
      hosts:
         mail.example.com:
      children:
           webservers:
              hosts:
                 foo.example.com:
                 bar.example.com:
           dbservers:
              hosts:
                 one.example.com:
                 two.example.com:
                 three.example.com:
                                  
   ```
 
#### **2. Playbook**

- ***Set of Tasks***

- Just like in the programming world we have loops and functions and all, In the world of ansible we have a playbook.

- Playbook is actually a set of instructions to perform.

- Run OS update, Create differents users, etc

- In the playbook, you define all the things that you want to do like OS-Upgrade from all virtual machines, you want to do engineX update, apachhe update that is only update in a single virtual machine.

> ***Ansible is talking to so many of machines, so It's not recommended to put your all configuration on local machine, you should use some third party machine that is where ansible offers you a **Tower** which is a GUI/command line interface and it allows you to have a very graphical interface for all these things.***

