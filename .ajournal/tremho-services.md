

# Tremho Services

We're going to need a public server for much of the next set of general development tasks

This will facilitate, among other things:

- distribution site for DoW
- SSO listening service for Alcaeus and Prepared (For Dinner)
- general web stuff
- all other services of Alcaeus and Prepared.

##### Wagging the dog by the tail

We'll replicate what we did to set up an AWS EC2 like we did for Wagtales

nginx is the front end.  

basically, it's set up per [this guide](https://medium.com/@nishankjaintdk/setting-up-a-node-js-app-on-a-linux-ami-on-an-aws-ec2-instance-with-nginx-59cbc1bcc68c)

We'll create our Node services in the project tremho-services

###### 8/31 10:18am
I've got the ec2 setup and a 'connect' script to connect to it in tremho-services.
I've installed nvm, node, and git so far.

Now I need to make the node services project skeleton so I can deploy it here and get on to the ngnx setup parts.

This readme will likely continue in the tremho-services space.  TTFN



