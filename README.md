## 🎯 A Template for Sample Docker Guides 


This page outlines the requirements for writing Docker User Guides. This repository is meant to support Docker guides only. 
If you have any questions, please contact `#docs` on the [Docker Community Slack](https://communityinviter.com/apps/dockercommunity/docker-community)

>  [!TIP]
>
> Please remove this "A Template for Sample Docker Guides" section from the README file after cloning the repository to ensure your guide is clean and tailored to your specific application.



1. Select **Use this template** and choose **Create a new repository**.

<img width="1144" alt="image" src="https://github.com/user-attachments/assets/d27634f1-1f7e-4e77-bc60-25122467e805">

---


2. Select **dockersamples/docker-guides-template** under Repository Template, select your repository, populate description and choose your preferred repository name.

<img width="725" alt="image" src="https://github.com/user-attachments/assets/8fbc6a38-f6ab-4442-b0ad-51ad01794016">

---



3. Select **Create repository**. Don't forget to populate **About** section with a short description of the project once you create the repository.


## Title of the guide

Your title should clearly state the main focus of the guide and the technology being used. Keep it concise and informative.

> [!TIP]
> - Developing event-driven applications with Kafka and Docker- [Link](https://docs.docker.com/guides/use-case/kafka/)
> - Develop and test AWS Cloud applications using LocalStack and Docker

## Introduction

Start with a brief introduction that explains the problem being addressed and why the guide is important. Provide some context on the technology stack involved.

> [!TIP]
> With the rise of microservices, event-driven architectures have become increasingly popular. Apache Kafka, a distributed event streaming platform, is often at the heart of these architectures. Unfortunately, setting up and deploying your own Kafka instance for development is often tricky. Fortunately, Docker and containers make this much easier.

## Learning Objectives

Outline what users will learn by following your guide. Break this down into specific tasks or skills they will gain.

> [!TIP]
> In this guide, you will learn how to:
> 
> - Use Docker to launch a Kafka cluster
> - Connect a non-containerized app to the cluster
> - Connect a containerized app to the cluster
> - Deploy Kafka-UI to help with troubleshooting and debugging

## [Prerequisite](https://docs.docker.com/guides/use-case/kafka/#prerequisites)

List the prerequisites required to follow along with the guide. Be specific about any tools, software versions, and technical knowledge that the user must have before starting.

> [!TIP]
> - [Docker Desktop](https://www.docker.com/products/docker-desktop/)
> - [Node.js](https://nodejs.org/en/download/package-manager) and [Yarn](https://yarnpkg.com/)
> - Basic knowledge of Kafka and Docker

## Step-by-Step Instructions

The main part of the guide should be clear, concise, and broken into manageable steps. Each step should include the necessary code, command-line instructions, and context to ensure that users can follow along without confusion.

> [!TIP]
> [Example Section - Launching Kafka](https://docs.docker.com/guides/use-case/kafka/#launching-kafka)
> 
> Starting with Kafka 3.3, setting up Kafka for local development has been simplified due to KRaft mode. This section will guide you through launching a Kafka cluster using Docker.


> [!TIP]
> 1. Clone the GitHub repository:
>
> ```
> git clone https://github.com/dockersamples/kafka-development-node.git
> ```
> 2. Install dependencies:
> 
> ```
> yarn install
> ```
>
> 3. Start the app:
> 
> ```
> yarn dev
> ```

### Additional Setup for Containers


Where necessary, include diagrams or visuals to aid comprehension. For example, a diagram explaining Kafka listeners and how they work in both host and Docker connections can be added.
If applicable, explain how to modify the configuration to support containerized applications. Include information about port mappings, networking, and any environment variables needed.

## Diagrams and Visuals

Where necessary, include diagrams or visuals to aid comprehension. For example, a diagram explaining Kafka listeners and how they work in both host and Docker connections can be added.


## Adding Visualizers or Debugging Tools

For troubleshooting or monitoring, show how to add additional services like Kafka-UI for visualization.

> [!TIP]
> 
> Add the Kafka-UI service to your docker-compose.yml:
> 
> ```
> services:
>   kafka-ui:
>    image: ghcr.io/kafbat/kafka-ui:latest
>     ports:
>       - 8080:8080
>    environment:
>      KAFKA_CLUSTERS_0_NAME: local
>      KAFKA_CLUSTERS_0_BOOTSTRAPSERVERS: kafka:9093
> ```

> Access the Kafka-UI at `http://localhost:8080` to monitor your cluster.

## Testing and Validation

   > [!TIP]
   > To test that messages are being successfully published and consumed:
   > ### Open a Kafka console producer:
   > ```
   > docker exec -ti kafka /opt/kafka/bin/kafka-console-producer.sh --bootstrap-server :9092 --topic demo
   >  ```
   > ### Send a message:
   > ```
   > Test message
   >```

Provide instructions on how users can test and validate that everything is working as expected. This can include running scripts, checking logs, or using visual tools.

## Recap

Summarize what the user has achieved by completing the guide. Highlight key takeaways and encourage the user to explore further.


