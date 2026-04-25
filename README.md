# URL Shortener
This project is a full-stack URL shortener built to reinforce core system design concepts through hands-on implementation. It follows a structured design framework commonly used in large-scale system design.

The initial version of this project focuses on core functionality (URL creation and redirection), with additional features introduced incrementally.

## Design Framework

This project follows a structured system design approach:

1. Requirements
2. Core Entities 
3. API Interface
4. High Level Design
5. Deep Dives

## Requirements

**High level description of the project:** A full-stack URL shortener that allows users to create, store, and manage short links that redirect to their original URLs.

**Note:** Core requirements are denoted using "shall," while optional requirements are denoted using "should." 

### Functional Requirements (Core)
1. The system shall allow a user to submit a long URL.
2. The system shall generate a unique short URL for the submitted link.
3. The system shall return the shortened URL to the user.
4. The system shall store the mapping between the short URL and the original URL.
5. The system shall redirect the user to the original URL when the shortened URL is accessed.
6. The system shall handle requests for non-existent short URLs with an appropriate error response.

### Functional Requirements (Extended/Optional)
1. The system should allow the user to specify a custom short alias.
2. The system should support setting an expiration date for short URLs.
3. The system should track the number of times a short URL is accessed.
4. The system should allow the user to retrieve metadata about a short URL.
5. The system should allow the user to delete a short URL.
6. The system should allow the user to update the destination URL.

### Non-Functional Requirements
1. Redirects should be fast (low latency).
2. The system shall be reliable and consistently return correct redirects.
3. The system should scale to handle high volumes of URL creation and redirection requests.
4. The shortened URLs shall be concise and easy to share.
5. The system shall be secure against common input-based attacks (e.g. malformed URLs).


## Core Entity

The project is centered around shortened URLs created from long URLs provided by the user. Therefore, this project has a single core entity: `short_urls`.

## API Interface

The following endpoints support the core functionality of creating, retrieving, and resolving short URLs:

### `POST /short_urls`     # Create a new short URL

Purpose: Create a new short URL.

Request: 
- The user provides a long URL (required)

Request Body:

`{

    "originalUrl": ""

}`


### `GET /short_urls/{identifier}`     # Get the metadata for a short URL

### `GET /{identifier}`     # Redirect to the original URL