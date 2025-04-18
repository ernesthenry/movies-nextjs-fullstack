# Movie App

A modern, responsive movie browsing application built with Next.js that allows users to explore movie details using The Movie Database (TMDB) API. The app includes user authentication features and a clean, responsive interface.

![Movie App Screenshot](https://via.placeholder.com/800x400?text=Movie+App+Screenshot)

## Features

- **Movie Browsing**: Browse through a collection of movies from TMDB
- **Movie Details**: View comprehensive information about each movie including:
  - Title, release date, and runtime
  - Genres with interactive buttons
  - Status information
  - Overview and descriptions
- **Responsive Design**: Optimized for both desktop and mobile viewing
- **User Authentication**: Secure login and registration system
- **MongoDB Integration**: User data securely stored in MongoDB

## Tech Stack

- **Frontend**: Next.js, React, TypeScript
- **Styling**: Tailwind CSS
- **Authentication**: bcrypt.js for password hashing
- **Database**: MongoDB with Mongoose
- **API**: TMDB (The Movie Database) API

## Prerequisites

Before running this project, make sure you have:

1. Node.js (v14 or newer)
2. MongoDB instance (local or cloud-based like MongoDB Atlas)
3. TMDB API key (get one from [TMDB website](https://www.themoviedb.org/documentation/api))

## Environment Variables

Create a `.env.local` file in the root directory with the following variables:

```
# Database
DB_URI=your_mongodb_connection_string
SALT_WORK_FACTOR=10

# API
API_KEY=your_tmdb_api_key

# Auth (optional)
JWT_SECRET=your_jwt_secret
```

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/ernesthenry/mmovies-nextjs-fullstack.git
   cd movies-nextjs-fullstack
   ```

2. Install dependencies:
   ```bash
   npm install
   # or
   yarn install
   ```

3. Run the development server:
   ```bash
   npm run dev
   # or
   yarn dev
   ```

4. Open [http://localhost:3000](http://localhost:3000) with your browser to see the application.

## Project Structure

```
movie-app/
├── app/                  # Next.js app directory
│   └── [movie]/          # Dynamic route for movie details
├── components/           # Reusable React components
│   ├── Button.tsx        # Custom button component
│   └── BackButton.tsx    # Navigation button component
├── lib/                  # Utility functions
│   └── dbConnect.js      # MongoDB connection helper
├── models/               # Mongoose models
│   └── User.js           # User authentication model
├── public/               # Static assets
├── .env.local            # Environment variables (create this)
└── README.md             # This file
```

## API Integration

The app uses TMDB API to fetch movie data. API calls are made server-side in Next.js to protect your API key and improve performance through caching.

Example API endpoint:
```
https://api.themoviedb.org/3/movie/{movie_id}?api_key={your_api_key}
```

## Authentication Flow

1. User registers with email, name, and password
2. Password is hashed using bcrypt before storing in MongoDB
3. On login, entered password is compared with stored hash
4. Authentication state is managed using secure HTTP-only cookies

## Deployment

This app can be easily deployed on Vercel:

1. Push your code to a GitHub repository
2. Import the project in Vercel
3. Set up the environment variables
4. Deploy!

For other deployment options, refer to the [Next.js deployment documentation](https://nextjs.org/docs/deployment).

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- [Next.js](https://nextjs.org/) for the React framework
- [TMDB](https://www.themoviedb.org/) for the movie data API
- [Tailwind CSS](https://tailwindcss.com/) for styling
- [Mongoose](https://mongoosejs.com/) for MongoDB object modeling