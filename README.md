# Devops_Task
DevOps Technical Assessment
DevOps Technical Assessment
This is not a test but rather a conversation starter. Have fun with the task, and we can’t wait to
discuss your work during our meeting.
Deploy to Kubernetes cluster one of the applications prescribed in this task ("Applications set"
part).
Some requirements for the application deployment:
1. It should be highly available and scalable: The application has to be fault-tolerant regarding
the loss of one cluster node and automatically scalable depending on the CPU load available
across multiple nodes.
2. Give an example of how you would expose secure credentials as an environment variable.
It could be faking the database connection even if the app doesn't need one.
3. If the application is stateful - then it should have a persistent volume configuration.
4. You should make use of the readiness and liveness probe as much as feasible.
5. If possible, Ingress should be deployed for the opportunity to access the application
outside of the private network
1 and 2 are must-have requirements. The rest is something to consider and work with, you
can also choose to demonstrate anything else you think is useful to do with this application on
a Kubernetes deployment, be creative and surprise us, but most importantly, have fun with the
task.
Tech stack to use:
1. Kubernetes is the only requirement as a platform. To manage the deployment descriptors
you can use any other tool you prefer as long as you can argue for it, can be a set of
YAML files or a system like Helm or anything in between.
2. GitHub. The application should be visible together with Kubernetes specs and Dockerfile
in GitHub repository. You might be able to fork the project from one of the applications.

Applications set:
1. It might be your own pet project application which could be accessed by HTTP or
anything else you fancy deploying as long as it has a HTTP/REST interface, so can also
be the Nginx Test site.
2. Django app
3. Node.js app (you need to correct npm commands in Dockerfile in this case)
Follow-up questions that you can think about or answer already, but they also serve
as an example of what you can expect as discussion in the follow-up
presentation:
1. Where and how did you set up the Kubernetes cluster? Why did you consider this
option? How would you handle the cluster setup next time you'll need a new one? 2.
How would you improve the application setup?
a. Would you go with CI/CD pipeline? If so, which one?
b. Would you template the setup? If so, which tool would you choose for that? c.
How would you monitor the application? What kind of metrics would you choose
and what monitoring system would you pick up?
3. How would you scale the application setup across multiple regions?

