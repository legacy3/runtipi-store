# Qdrant

Qdrant is a vector database & vector similarity search engine. It deploys as an API service providing search for the nearest high-dimensional vectors. With Qdrant, embeddings or neural network encoders can be turned into full-fledged applications for matching, searching, recommending, and much more!

## Features

- **High Performance**: Written in Rust for maximum performance and reliability
- **Vector Search**: Efficient similarity search in high-dimensional vector spaces
- **RESTful API**: Easy to integrate with any application via HTTP API
- **Filtering**: Advanced filtering capabilities for precise search results
- **Scalability**: Horizontal scaling support for large datasets
- **Multiple Distance Metrics**: Support for Cosine, Euclidean, and Dot product distances
- **Payload Support**: Store additional metadata alongside vectors
- **Real-time Updates**: Add, update, and delete vectors in real-time

## Use Cases

- **Semantic Search**: Find documents, images, or other content based on meaning
- **Recommendation Systems**: Build personalized recommendation engines
- **Image Search**: Search for similar images using visual embeddings
- **Chatbots & AI**: Power conversational AI with semantic understanding
- **Anomaly Detection**: Identify outliers in high-dimensional data
- **Duplicate Detection**: Find similar or duplicate content

## API Endpoints

- **Web UI**: Access the Qdrant dashboard at the main port (6333)
- **REST API**: Full REST API available at port 6333
- **gRPC API**: High-performance gRPC interface at port 6334

## Getting Started

1. Install the app through Runtipi
2. Access the Qdrant dashboard via the web interface
3. Create your first collection using the API or dashboard
4. Start inserting vectors and performing searches

For detailed API documentation and examples, visit the [official Qdrant documentation](https://qdrant.tech/documentation/).

## Storage

Qdrant data is persisted in the `/qdrant/storage` directory, which is automatically mapped to your Runtipi app data directory for persistence across container restarts.