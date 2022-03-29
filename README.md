# horizon-project

### Horizon project is a suit of services that compose up a web application to serve tv show media contents to users.
### Core Features:
#### 1.Microservice Architecture.
#### 2.Event Driven.
#### 3.HLS (Http Live Streaming) based.
#### 4.JWT (JSON webtoken) authentication system.
#### 5.Native APIs.
#### 6.Encoding Media Content.
#### 7.Native Azure services.

### Services:
#### 1.UI (Angular): the client side of the application created in angular implemented in a reactive manner.
#### 2.Show Service (Spring Boot): A service which serves show data in json format. HATEOAS principle is applied here. This service is accessed either through the UI to fetch data, or through the horizon controller service to add new show data. This service is integrated with a PostgreSQL database as the central database.
#### 3.User Service (Spring Boot): A service that implements user authentication using JWTs. The database connected with this service is the central database (PostgreSQL).
#### 4.Media Service (Node.js): This service is an implementation of an HLS server that serves media content. The content is either TS files (videos in small chunks) or images. This service is integrated with the main storage (Horizon storage).
#### 5.Hub Service (Node.js): A service that resembles a social app where users can post reviews and suggestions about existing shows. It is connected to Hub database (MongoDB).
#### 6.A. Show Service Controller (Svelte): A controller service which should be ran from localhost (or any host that stores content locally). This service which is connects to the central database acts as a pannel to add tv shows and episodes and upload content to the other integrated components in the cloud. It should be ran along with the Controller Server that connects directly to the central storage.
#### 6.B. Show Service Controller (Node.js): The server side of the controller which recieves content and uploads them to the horizon storage.

### Other Components:
#### * Central Database - PostgreSQL: The central database which contains relations and data about tv shows, episodes, tv show images and episode images. It also persists the relation between their entities.
#### * Hub Database - MongoDB: A secondary database that holds data about reviews and suggestions which users create about shows.
#### * Horizon Storage - Azure Storage: A premium-tier storage that contains all files related to content being served: images and TS files.
#### * Event Bus - RabbitMQ: An event bus set up to satisfy event-driven pattern of the following relations: User Service - Hub Service; Show Service - Hub Service.

#### The following lucid chart shows the overall architecture of the application:
https://lucid.app/lucidchart/c8fb233e-7903-4fae-9492-bd475e95dfa7/edit?invitationId=inv_6ed20c5a-f153-4398-b092-bd027f05b3cc

