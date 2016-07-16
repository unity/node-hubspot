# node-hubspot

Node.js wrapper for the HubSpot API

## Installing

npm install hubspot

## Usage

    var Client = require('hubspot');

    var client = new Client();

    /*
     * You can use either a key OR a token
     */
    if (config.key) {
      client.useKey(config.key);
    } else if (config.token) {
      client.useToken(config.token);
    }

    if (config.key) {
        client.setApiKey(config.key)
    } else if (config.access_token){
        client.setAccessToken(access_token);
        if (config.refresh_token) {
            client.setRefreshToken(refresh_token);
        }
    }
    client.setClientId(config.client_id);
    client.refreshAccessToken(function(/* err, token */) {});

    client.campaigns.get(function(err, res) {
      if (err) { throw err; }
      console.log(res);
    });

## Available Methods

### Companies

    client.companies.getRecentlyCreated(opts, cb)

### Contacts

    client.contacts.get(opts, cb)
    client.contacts.getByEmail(email, cb)
    client.contacts.getByEmailBatch(emails, cb)
    client.contacts.getById(id, cb)
    client.contacts.update(id, data, cb)
    client.contacts.create(data, cb)
    client.contacts.createOrUpdateBatch(data, cb)

### Lists

    client.lists.get(opts, cb)
    client.lists.getOne(id, cb)
    client.lists.getContacts(id, opts, cb)
    client.lists.getRecentContacts(id, opts, cb)
    client.lists.addContacts(id, contactBody, cb)

### Files

    client.files.get(cb)
    client.files.getOne(id, cb)

### Email

    client.subscriptions.get(opts, cb)

### Email Events

    client.campaigns.get(opts, cb)
    client.campaigns.getOne(id, appId, cb)
    client.campaigns.events(opts, cb)

### Social Media

    client.broadcasts.get(opts, cb)

### Properties

    client.properties.get(cb)
    client.properties.getOne(property_name, cb)

## License

MIT

## Contributors

Brian Falk @brainflake

Tim Atkinson @timisbusy

Tejas Manohar @tejasmanohar

Krispin Schulz @kr1sp1n
