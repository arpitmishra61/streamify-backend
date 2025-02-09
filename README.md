# Streamify Dashboard API

A simple REST API server for the Streamify Dashboard application using json-server.

## Prerequisites

- Node.js (v14 or higher)
- npm (Node Package Manager)

## Installation

1. Clone the repository:

```bash
git clone https://github.com/arpitmishra61/streamify-backend
```

2. Install dependencies:

```bash
npm install
```

## Usage

### Local Development

To start the server locally:

```bash
npm start
```

The server will start running on `http://localhost:3001` by default.

### Production API

The API is deployed and available at:

```
https://streamify-backend-2nzg.onrender.com
```

You can access all the API endpoints using this base URL. For example:

```bash
# Get all streams
GET https://streamify-backend-2nzg.onrender.com/streams

# Get key metrics
GET https://streamify-backend-2nzg.onrender.com/keyMetrics

# Get top 5 streams by count
GET https://streamify-backend-2nzg.onrender.com/streams?_sort=streamCount&_order=desc&_limit=5
```

## API Endpoints

The following endpoints are available:

### Streams

- `GET /streams` - Get all stream records
- `GET /streams/:id` - Get a specific stream by ID
- `GET /streams?userId=:userId` - Get streams for a specific user
- `GET /streams?_sort=dateStreamed&_order=desc` - Get streams sorted by date

### Key Metrics

- `GET /keyMetrics` - Get overall platform metrics including:
  - Total Users
  - Active Users
  - Total Streams
  - Revenue
  - Top Artist

### Revenue Distribution

- `GET /revenueDistribution` - Get revenue breakdown by category:
  - Premium Subscriptions
  - Ad Revenue
  - Merchandise
  - Other

### Top Songs

- `GET /topSongs` - Get list of top performing songs with stream counts

### User Growth

- `GET /userGrowth` - Get historical user growth data by month

### Filtering and Sorting

- Use `_sort` and `_order` parameters for sorting
- Use `_limit` parameter to limit results
- Use property names as query parameters for filtering

Example:

```bash
GET /streams?_sort=streamCount&_order=desc&_limit=5
```

## Dependencies

- cors: ^2.8.5 - Enable CORS (Cross-Origin Resource Sharing)
- json-server: ^0.17.4 - Full fake REST API server

## Development

To modify the API:

1. Update the data in `db.json`
2. Modify routes in `server.js`

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.
