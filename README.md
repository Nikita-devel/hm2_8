[Main page](https://github.com/Nikita-devel) | [Python Web Page](https://github.com/Nikita-devel/Python_Web)

# MongoDB, RabbitMQ, and Email Simulation Project

## Overview

This repository documents a Python project focusing on the integration of MongoDB for data storage, RabbitMQ for message queuing, and simulated email distribution. The project is divided into two primary parts.

## Part 1: MongoDB and Quotes Search

### MongoDB Setup and Data Models

The project commences with the establishment of a MongoDB Atlas cloud database. Two data models, `Author` and `Quote`, are crafted using the Mongoengine ODM. The `Author` model contains information about authors, while the `Quote` model stores quotes with corresponding tags and author references.

### Data Seeding and Search Script

A script, `seed_mongo.py`, is implemented to load data from JSON files (`authors.json` and `quotes.json`) into the MongoDB database. Additionally, a search script, `search_quotes.py`, is provided for users to search for quotes based on author names, tags, or a combination of tags.

### Additional Tasks

The search script supports shorthand commands for convenience (`name:st` instead of `name:Steve Martin`). Caching of search results is implemented using Redis, enhancing performance by retrieving results from the cache.

## Part 2: RabbitMQ and Email Simulation

### RabbitMQ Setup and Contact Model

The second part centers around simulating email distribution using RabbitMQ. Two scripts, `producer.py` and `consumer.py`, are developed for this purpose. The `Contact` model, designed with the Mongoengine ODM, encompasses fields such as full name, email, phone number, and a logical field indicating whether a message has been sent.

### Email Simulation Workflow

The `producer.py` script generates fake contacts, writes them to the MongoDB database, and places messages in the RabbitMQ queue, each containing the ObjectID of the created contact. Subsequently, the `consumer.py` script processes these messages, simulates sending emails (via a placeholder function), and updates the logical field accordingly.

### Additional Task

An additional feature is introduced to manage user preferences for message delivery, allowing messages to be sent via both email and SMS based on contact preferences. Two distinct queues (`consumer_sms.py` and `consumer_email.py`) are established to handle contacts for SMS and email, respectively.

## Conclusion

This project serves as a comprehensive demonstration of the integration of MongoDB, RabbitMQ, and simulated email distribution. It underscores aspects such as data modeling, database seeding, search functionalities, and efficient message queuing for effective communication simulation. The incorporation of advanced features like Redis caching and user preferences contributes to the project's robust and versatile nature.
