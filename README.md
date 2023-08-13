# Movie Rating Application

The Movie Rating Application is a web-based platform that allows users to rate and review movies. It provides features for submitting ratings, viewing movie details, and calculating overall movie ratings. The application integrates with external APIs to fetch additional details such as pincode information.

## Features

1. **Create Movie:** Users can create new movie entries by providing the movie name and pincode.

2. **View Movie Details:** Users can retrieve detailed information about a specific movie using its ID.

3. **View All Movies:** The application provides a list of all available movies.

4. **View Movies by Pincode:** Users can fetch movies based on a specific pincode.

5. **Submit Ratings:** Users can rate and review movies, providing a rating between 1 and 10 along with optional comments.

6. **View Movie Ratings:** Users can view all ratings and reviews for a specific movie.

7. **Calculate Overall Movie Rating:** The application calculates the overall rating for a movie based on user ratings.

8. **Fetch Pincode Details:** Users can fetch details about a pincode, including post office information.

9. **Fetch Post Office Details:** Users can fetch details about a post office.

## Project Structure

The project is structured as follows:

- `com.movieratingapp.application`: Root package
    - `MovieRatingAppApplication`: The main application class containing the `main` method.
    - `config`: Contains configuration classes if any related to Postal Pincode API
    - `controller`: RESTful controller classes for different functionalities.
    - `dto`: Data Transfer Object classes used for transferring data between layers.
    - `entity`: JPA Entity classes representing database tables.
    - `exception`: Custom exception classes.
    - `repository`: Spring Data JPA repository interfaces.
    - `service`: Service classes implementing business logic.
    - `PincodeResponse`: POJO class for mapping the response from the pincode API.

## External APIs

The application integrates with the [Postal Pincode API](https://api.postalpincode.in/) to fetch details about pincodes and post office.

## API Endpoints

### Movie Controller

- **Create Movie:**
  - Endpoint: `POST /movies`
  - Request Body: MovieEntity (JSON)
  - Creates a new movie entry.

Create a new movie entry.
#### Request Body
```json
{
    "movieName": "Inception",
    "pincode": "123456"
}


- **Get Movie Details:**
  - Endpoint: `GET /movies/{movieId}`
  - Returns detailed information about a specific movie.

- **Get All Movies:**
  - Endpoint: `GET /movies`
  - Returns a list of all available movies.

- **Get Movies by Pincode:**
  - Endpoint: `GET /movies/pincode/{pincode}`
  - Returns movies based on a specific pincode.

### Rating Controller

- **Submit Rating:**
  - Endpoint: `POST /ratings`
  - Request Body: RatingDTO (JSON)
  - Submits a new rating and review for a movie.
Submit a new rating entry.
#### Request Body
```json
{
    "movieId": {
        "movieId": 1,
        "movieName": "Inception",
        "pincode": "123456",
        "ratings": []
    },
    "userId": 1,
    "userName": "JohnDoe",
    "ratingValue": 9,
    "reviewComments": "Mind-bending movie with stunning visuals."
}


- **Get Movie Ratings:**
  - Endpoint: `GET /ratings/movie/{movieId}`
  - Returns all ratings and reviews for a specific movie.

- **Get Overall Movie Rating:**
  - Endpoint: `GET /ratings/movie/{movieId}/overall`
  - Calculates and returns the overall rating for a movie.

### Pincode Controller

- **Get Pincode Details:**
  - Endpoint: `GET /pincode/{pincode}`
  - Returns details about a specific pincode.
- **Get Post Office Details:**
  - Endpoint: `GET /pincode/search/{postoffice}`
  - Returns details about a specific post office.

## Getting Started

1. Clone the repository to your local machine.
2. Configure your database settings in `application.properties`.
3. Build and run the application using a Java IDE or Gradle/Maven command.

## Usage

1. Access the API endpoints using a tool like `curl`, Postman, or any REST client.
2. Follow the API documentation for details about available endpoints and request/response structures.

## Contributing

Contributions are welcome! Feel free to fork the repository, make changes, and submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
