# metallb add-on

This README provides steps to install metallb load balancer for Kubernetes cluster as Nirmata add-on.

## When to use metallb?
Public cloud providers offer loadbalancer type service which makes it easy to expose an applicaation outside the cluster. Metallb provides similar service for applications running on on-prem clusters.
Metallb requires a routable ip range to provide an IP address to the services exposed outside the cluster.
Metallb can support either layer-2 mode or BGP mode to access the service and advertise the routes.
This configuration is tested in layer-2 mode.
Tested Version - 0.8.3


## How do I get set up?
1. Use the yaml available in the repo and import it into your default-add-on catalog in Nirmata. Edit the catalog application and select an add-on category (eg: Networking). This is required to select the application as an add-on.
2. Cutomize the ip address range in the configmap based on your design.
3. Go to your cluster in Nirmata, select add-on tab and choose deploy add-on from the catalog. Ensure that the namespace you use is "**metallb-system**"
4. Now, go to your application that you want to expose and choose expose the deployment option
5. Choose the service type as loadbalancer and configure the ports.
6. Deploy the application and once it is running , verify that the service type load balancer waas assigned an IP address from the ip range.
  
## Issues?
For issues, please reach out to support@nirmata.com
