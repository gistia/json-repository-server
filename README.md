# Sample JSON Repository server

## Instructions

Clone the JSON Repository repository:

```
cd ~/code
git clone git@github.com:gistia/json-repository.git
```

Install its dependencies and make the json-repository library available locally:

```
cd ~/code/json-repository
npm install
npm link
```

Clone this repo:

```
cd ~/code
git clone git@github.com:gistia/json-repository-server.git
```

Link the local json-repository npm library and install dependencies:

```
cd ~/code/json-repository-server
npm link json-repository
npm install
```

Configure your .env:

```
cp .env.example .env
```

Edit its settings and then finally run the server:

```
npm start
```

There will be two routes available:

```
GET  /:collection/:id -- retrieves a document by id
POST /:collection     -- creates a new document or a new version of the document
```

## Testing

To send new JSON payloads, you can use one of the two commands below.

### Posting a JSON file contents

```
curl -v  -H 'Content-type: application/json' -X POST http://localhost:8080/results -d @./path/to/json/file.json
```

### Posting a JSON string

```
curl -v  -H 'Content-type: application/json' -X POST http://localhost:8080/results -d '{"this": "is", "my": "json"}'
```
