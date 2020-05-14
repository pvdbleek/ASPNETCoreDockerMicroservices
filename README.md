# ASPNET MicroServicesDemo on k8s

This repo was kindly borrowed from: [https://github.com/mmacneil/ASPNETCoreDockerMicroservices](https://github.com/mmacneil/ASPNETCoreDockerMicroservices)

### Orginal documentation:
[https://github.com/mmacneil/ASPNETCoreDockerMicroservices/blob/master/README.md](https://github.com/mmacneil/ASPNETCoreDockerMicroservices/blob/master/README.md)

## Deploying this version:
This repo has been modified from the original to:

* Accomodate app builds in containers, so you don't need anything else besides docker on your system.
* Made it more friendly to k8s and less dependant on docker-compose.

1. Clone this repo to your local system
2. **(Optional)** Perform a docker build for `Web`, `Services\Applicants.Api`, `Services\Jobs.Api`, `Services\Identity.Api`
3. **(Optional)** Push the images to a registry of your choice (the k8s yaml files include my pre-built images on docker hub, which should work fine as well)
4. Make sure you have a MS SQL Server available, it can be reached from your k8s cluster and has a user account which can login remotely.
5. Deploy the `sql` script in `Database` to create & populate the database
6. Adjust the yaml files in `k8s` to include the correct DB connection string and your optional images.
7. Deploy the yaml files to your cluster


