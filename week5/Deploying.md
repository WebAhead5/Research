# Deploying


## what is a cloud service/Cloud platform?

Cloud computing is the on-demand availability of computer system resources, especially data storage and computing power over the Internet (“the cloud”), without direct active management by the user.  [Cloud Services Explained - tutorial for beginners](https://www.youtube.com/watch?v=1ERdeg8Sfv4)

You typically pay only for cloud services you use, helping you lower your operating costs, run your infrastructure more efficiently, and scale as your business needs change.

There are three main models for cloud computing.

- <u><b>IaaS (Infrastructure as a Service):</b></u> In IaaS, you rent IT infrastructure—servers and virtual machines (VMs), storage, networks, operating systems—from a cloud provider on a pay-as-you-go basis.

- <u><b>PaaS (Platform as a Service):</b></u>  PaaS is designed to make it easier for developers to quickly create web or mobile apps, without worrying about setting up or managing the underlying infrastructure. [(PaaS Explained)](https://www.youtube.com/watch?v=QAbqJzd0PEE)

- <u><b>SaaS (Software as a Service):</b></u> Software as a service is a method for delivering software applications over the Internet, cloud providers host and manage the software application and the underlying infrastructure. (for example: Office 365, google suite)


for more about Cloud Computing Services Models [click here](https://www.youtube.com/watch?v=36zducUX16w).




## Why is it useful to be able to deploy your code to a cloud platform, rather than running it locally? 
- <b>💰 Cost</b>: Cloud computing eliminates the capital expense of buying hardware and software and setting up and running on-site datacenters .
-  <b>🌐 Global scale</b>: The ability to scale elastically. In cloud speak, that means delivering the right amount of IT resources. (computing power, storage, bandwidth, etc...)

- <b>👮 Security</b>: Many cloud providers offer a broad set of policies, technologies, and controls that help protect your data, apps, and infrastructure from potential threats.

- <b>🚋 Speed</b>: Most cloud computing services are provided self service and on demand, so even vast amounts of computing resources can be provisioned in minutes,


## What services are there that can provide you with a platform for your code? 




1. 📒 <b> [Heroku](http://www.heroku.com/) </b> is one of the oldest PaaS services out there. It supports running applications written in Ruby, Java, PHP, Node.js, and others, as well as deploying applications in Docker containers. Heroku offers a free tier, however, the application will be put to sleep after 30 minutes of inactivity.

1. 📒 <b> [Netlify](https://www.netlify.com/) </b> is a service for hosting static websites. It offers a fully fledged free tier with support for automated deployment, HTTPS, redirects, A/B testing, form submission and backend logic using AWS Lambda functions.

3. 📙 <b>[Microsoft Azure](https://azure.microsoft.com/en-us/) </b> An App Service that allows hosting applications written in different languages on both Windows or Linux, as well as running Docker applications. There’s a free shared instance available for the Windows app service.
4. 📙 <b> [Google App Engine](https://cloud.google.com/appengine) </b> is a service on Google Cloud that supports deploying applications written in Java, Python, Node.js, Go and PHP and Docker applications. There’s also a limited free tier available.


## Further Reading

- [microsoft azure - What is cloud computing?](https://azure.microsoft.com/en-us/overview/what-is-cloud-computing/#cloud-deployment-types)
- [aws Amazon - Types of Cloud Computing.](https://aws.amazon.com/types-of-cloud-computing/)
- [Advantages and Disadvantages Of Cloud Computing.](https://www.guru99.com/advantages-disadvantages-cloud-computing.html)

----------------------------------------------------------------------

## Environment variables
An environment variable is a dynamic-named value that can affect the way running processes will behave on a computer

In all Unix and Unix-like systems, each process has its own separate set of environment variables. By default, when a process is created, it inherits a duplicate environment of its parent process, except for explicit changes made by the parent when it creates the child

#### Checking existing variables
To see all the enviroment variables in linux use the command:

    $printenv
    
To check aspecific enviroment variable use the comand:

    $echo $VARIABLE_NAME

For a list of all environment variables command [Click here]('https://www.cyberciti.biz/faq/linux-list-all-environment-variables-env-command/')


#### Assign existing or new variables

    export VARIABLE=value
    







