# OpenAPI Learning
[[Fleeting Notes MOC]]
- For RestfulAPI documentation
- editor.swagger.io : if you want to make it without vscode
### DATA TYPE (format)
- integer (32)
- integer (64)
- number (float)
- number (double)
- string
- string (byte)
- string (binary)
- boolean
- string (date)
- string (date-time)
- string (password)
### OPEN API OBJECT
- openapi (string - REQUIRED - must be semantic version)
- info (info Object - REQUIRED)
- servers (server Object)
- paths (path Object - REQUIRED)
- components
- security
- tags
- externalDocs
### INFO OBJECT
- title (string) : REQUIRED
- description (string)
- termsOfService (string)
- contact (Contact Object)
- license (License Object)
- version (string)
### CONTACT OBJECT
- name (string)
- url (string)
- email (string)
### SERVER OBJECT
- url (string - REQUIRED)
- description (string)
- variables (Map[string, Server Variable Object])
- using variable = make it in curly brackets
### EXTERNAL DOCUMENTATION OBJECT
- description: string
- url: string (REQUIRED)
### PATH
- endpoint of API
- don't write all the url, only after the server
- Must begin with slash (/)
- Path Item object
	- $ref (reference)
	- summary (string)
	- description (string)
	- servers (Array of Server Object - better to use existing Server Object)
	- parameters (Array of Parameter Object)
- Path Operation (Operation Object)
	- get
	- put
	- post
	- delete
	- options
	- head
	- patch
	- trace
### OPERATION OBJECT
- The operation (HTTP Method) of the paths
- Object props:
	- tags (Array of strings)
	- summary (string)
	- description (string)
	- externalDocs (External Documentation Object)
	- operationId (string)
	- parameters (Array of Parameter Objects | Reference Object)
	- requestBody (Request Body Object | Reference Object)
	- responses (Response Object)
	- callbacks (Map[string, Callback Object | Reference Object])
	- deprecated (boolean)
	- security (Array of Security Requirement Object)
	- servers (Array of Server Object)
### PARAMETER
- Parameter is the info that we give without using requestBody (usually through url)
- OpenAPI detects the one that is from: Query Parameter, Path Variable, Header, Cookie
- We could add parameter within operation, so we can know what parameter that called that parameter
- Parameter Object:
	- name (string - REQUIRED)
	- in (string - REQUIRED): enum of (query, header, path, cookie)
	- description (string)
	- required (boolean - REQUIRED): is the parameter required 
	- deprecated (boolean)
	- allowEmptyValue (boolean)
### SCHEMA
- data type for the paramters
- parameter has schema attributes
- Important schema attributes
	- type (primitive json (string, boolean, etc))
	- default 
- Schema Validation attributes
	- maxLength
	- minLength
	- nullable 
	- etc...
- json-schema.org
### REQUEST BODY
- Can make schema validation for request body
- Request Body Object
	- description: string
	- content: Map[string, MediaType Object] (required)
	- required: boolean
- MediaType Object
	- schema
	- example
	- examples Map[string, Example Object | Reference Object]
	- encoding
- Object Schema: Having properties in schema so we could define what is inside the schema clearly properties by properties
- Array Schema: Having items properties in schema
### EXAMPLE
- Example object (implementation of schema) that should be the example of input
- Use "examples" for many example
- Can be used in parameters and request body
### RESPONSE BODY OBJECT
- Format:
	- HttpStatusCOde : Response Object | Reference Object
- Response Object:
	- description: string - REQUIRED
	- headers: Map[string, Header Object | Reference Object]
	- content: Map [string, Media Type Object]
	- links: Map [string, Link Object | Reference Objectf]
### TAG
- For grouping endpoints
- It is operation's attribute (operation's direct children)
### COMPONENT
- To save object that can be used repeatedly
- Component Object
	- schemas
	- responses
	- parameters
	- examples
	- requestBodies
	- headers
	- securitySchemas
	- links
	- callbacks
- Reference Object
	- Use Component in many object
### SECURITY
Security Object:
- type (string enum REQUIRED): apiKey, http, oauth2, openIdConnect
- description (string any)
- name (string applies to apiKey REQUIRED)
- in (string applies to apiKey enum REQUIRED): query, header, cookie
- scheme (string applies to http REQUIRED)
- bearerFormat (string applies to http("bearer"))
- flows (OAuthFlowsObject applies to oauth2 REQUIRED)
- openIdConnection (string applies to openIdConnect REQUIRED)
### CODEGENERATOR
- Go to editor.swagger.io
- Paste the json/yaml of our structured API
- Generate Client to generate the code