# Week 12
12/3/2014

### Course Logistics:
Formal requirements of the course
- Assignments due  Sat. 13th 
- Personal project due on the 19th 



## Servers and Remote Hosts
Today: Servers
- We will access servers
- We will address the movement from hardware to software
	- Recall: the Universal Turing Machine is both a material entity and an abstract one
	- In the early days of computing, there was a system admin (manager) and a developer
		- The sys admin used to be a less-valued, material labor (akin to the server "janitor") 
	- Now: we've moved from treating the server as a box to a server as software; the server is now an abstraction
- Cloud emulation: we can now emulate servers like Turing Machines
	- We can spin up emulations and automate them
	- Previously, large computers had to be physical computers and materially managed and rebooted to be synced
	- Now: "DevOps"
		- The rebirth of the systems administrator as a person who is no longer a computer janitor but a developer who is responsible for an orchestra of computers  

### What is a server?
- What is server
	- Simply: it is always on
	- A computer that is always on and listening  
- We often use "servers" that keep information not locally
	- it "serves" you data. It's always on and always listening
	- Examples: Webpage, live-streaming
	- listening to music is increasingly moved to a central server
- Servers are very very important
	- They run our companies, our government  
	- It's important to not just be clients but to be servers ourselves
	- On your client, what is requesting changes (eg, can be your application, your bash terminal)
	- We want to be running our own servers
		- Instead of buying new desktops, we're going to create one in the cloud

### What is "the cloud"?
- Another name for the cloud is "platform as a service", meaning that rather than buying the package, we ask for it served
	- We're going to be using Amazon AWS, but there are others (Google, etc).
- What the cloud does: it virtualizes the various components of what would be the server
	- What does this include: CPU (processing unit), an operating system, storage  
	- You can ask for a small provision of a server. 
	- These are *elastic* servers:
		- Normally you would buy a server. If you have high traffic, you have to expand that server.
		- On the cloud, if your traffic increases, then the server enlarges automatically
		- The elastic servers will shrink back down when traffic increases (you can set bounds on this)
- The parts of your computer are all virtual components (though underground somewhere there are physical computers)
	- CPU: On your computer, there are ports (eg "8080"), the same goes for a server
	- Storage: Normally, for a computer this is physical. On the cloud, this no longer a physical thing, but rather, an elastic block. This is a cloud equivalent to harddrives. 
		- S3, EBS, Glacier are all forms of backups  
	- There are other modular kinds of service components: database service, payment service, etc
	- Pay-per-use pay for monthly usage. 
- Big picture questions:
	- Rather than having that server in front of yourself, logging into the server will be the same experience. 
	- Most startups and formal companies are run off of this structure
	- Amazon takes this very very seriously (serves NSA, etc)
	- Because we did not physically secure the machine and the underlying structure of the instance, there could be ports, openings, backdoor access.
	- Should libraries buy their own servers or buy space on Amazon?
		- How comfortable are we with having a private entity managing this
		- Who should own the infrastructure of huge-record managing
- Amazon, when it was young
	- They have slightly different businesses, we're going to create internal services that can between departments.
	- Originally, "the cloud" was an internal service. It was then leased out (similar model in Paypal).
	- Amazon's innovation: providing not just one service but multiple
- Server communication
	- Say that your server is blocked 
		- You create a secure path to one server and then from there, access the blocked thing
		- This undermines the blocks that can happen at large centralized hubs.
	- Understanding information travel requires understanding network structure
	- Should we building architectures that support free speech online?
		- This is a security versus service problem: you need to ensure that no-one accidentally breaks the server, which leads us back to restricting permissions

## Amaon Web Services (AWS)
- From the homepage, we see the many different services
- Click on EC2 (this is the heart of the server)
- When you provision services in the cloud, you do it by regions (in our case, we're in the US East). This is one of the only hints as to where your stuff is. 
	- If you spin up a server, pick a service close by, so your packets don't need to travel far. 
	- NB: your components must be in the same region (eg, your stuff nees to be in the same region)
	- Companies who don't know where their users from will spin up redundent servers to reroute clients to 
- on the lefthand panel:
	- Limits: can limit your bandwith
	- Instances: this is where you can spin up servers. You can also reserve them in 
	- You can link sumer computers and emulate the computational power of supercomputing cluster
	- Select a free tier one
	- You can launch 1000 servers
		- De-dossing - you can automate this and then direct them all a website to crash it
	- If you're just doing computing, you can turn it on and off  