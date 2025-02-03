# test1
# OpenAPI Definition

## Version
**v0**

## Server
- **URL**: [http://localhost:8080](http://localhost:8080)  
  **Description**: Generated server url

## Paths

### POST /api/v1/webhook

- **Tags**: 
  - webhook-controller

- **Summary**: 
  Receive and save webhook

- **Description**: 
  This endpoint receives a webhook payload, verifies it, and saves it to the database if valid.

- **Operation ID**: 
  saveWebhookReflection

- **Request Body**:
  - **Required**: true
  - **Content**:
    - **application/json**:
      - **Schema**:
        - **Type**: string

- **Responses**:
  - **201**: 
    - **Description**: Webhook successfully saved
    - **Content**:
      - **\* / \***:
        - **Schema**:
          - **$ref**: `#/components/schemas/UnknownWebhookDto`
  
  - **400**: 
    - **Description**: Invalid webhook payload

## Components

### Schemas

#### UnknownWebhookDto

- **Required**:
  - body
  - uid

- **Type**: object

- **Properties**:
  - **uid**:
    - **Type**: string
    - **Format**: uuid
  - **created_at**:
    - **Type**: string
    - **Format**: date-time
  - **updated_at**:
    - **Type**: string
    - **Format**: date-time
  - **body**:
    - **Type**: string
