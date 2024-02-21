
# cassandra-paginator

Apache Cassandra® CQL lacks the `OFFSET` parameter that SQL and some other languages have. The `CassandraPaginator` is built to incorporate this abstraction, allowing you to paginate and "jump around" in the query results without needing to re-query the database. 

Cassandra Paginator is a utility library designed to facilitate efficient pagination of query results from Cassandra.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Installing

```bash
npm install cassandra-paginator
```

## Usage

Here's a quick example to get you started:

```javascript
const CassandraPaginator = require('cassandra-paginator');
const { Client } = require('cassandra-driver');

// Initialize your Cassandra client
const client = new Client({ contactPoints: ['localhost'], localDataCenter: 'datacenter1' });

// Create a new paginator instance
const paginator = new CassandraPaginator(client, "SELECT * FROM your_table WHERE condition = ?", ['value']);

// Fetch the first page of results
paginator.getPage(1).then(page => {
  console.log(page);
});
```

## API Documentation

For detailed API documentation, see [CassandraPaginator](classes\CassandraPaginator.CassandraPaginator.md).

## License

This project is licensed under the MIT License - see the [LICENSE.txt](LICENSE.txt) file for details.
