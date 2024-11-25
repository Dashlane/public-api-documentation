# Dashlane Public API Documentation

Welcome to the **Dashlane Public API Documentation**. This guide is designed for developers looking to integrate Dashlane into their applications. The Dashlane Public API provides access to valuable insights and functionalities related to your Dashlane team account, its members and their devices.

### Key Features

With the Dashlane Public API, you can:  

- Retrieve real-time team data, including roles, statuses, and usage metrics.  
- Automate administrative tasks to boost operational efficiency.  
- Analyze password health to identify weak, reused, or compromised credentials.  
- Monitor historical trends to strengthen organizational cybersecurity.  
- Develop custom solutions tailored to your workflows and integrate seamlessly with your existing systems.  

---

## Getting Started  

To begin using the Dashlane Public API, follow these steps:  

1. **Install the Dashlane CLI**  
   Download and [install the Dashlane CLI](https://cli.dashlane.com/install) on your machine.  

2. **Log in to Your Dashlane Account**  
   [Authenticate using the Dashlane CLI](https://cli.dashlane.com/personal/authentication) as a team administrator.  

3. **Generate an API Key**  
   Use the Dashlane CLI to create an API key:  

   ```bash
   dcli team public-api create-key "Description of the key"
   ```  

   The generated API key will follow this format:  
   `Bearer DLP_teamUuid_accessKey_secretKey`  

   **Important:** Store your API key securely as it will only be displayed once.  

   > ![NOTE]
   > Use the `DLP` prefix to identify and scan API keys in your codebase and prevent leaking this secret.  

4. **Authenticate Your Requests**  
   Add the API key to the `Authorization` header of your requests, as shown below:  

   ```bash
   curl -X POST \
   'https://api.dashlane.com/public/teams/Members' \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer DLP_teamUuid_accessKey_secretKey' \
   -d '{ }'
   ```  

---

## API Reference  

Dashlane provides an **OpenAPI 3.0 specification** to help you explore and utilize the Public API.  
- Download the specification [here](https://get.dashlane.com/public-api/openapi.json).  
- Alternatively, use the [Documentation UI](https://dashlane.github.io/public-api-documentation/) for a user-friendly interface to explore the available endpoints.  

---

## Managing API Keys  

You can manage your API keys directly from the Dashlane CLI:  

- **List All API Keys:**  
  ```bash
  dcli team public-api list-keys
  ```  

- **Revoke an API Key:**  
  ```bash
  dcli team public-api revoke-key <accessKey>
  ```  

---

## Contributing  

We welcome contributions to this project! If you have ideas or enhancements, feel free to fork the repository and submit a pull request. Please ensure that any contributions are either open source or your original work.  
