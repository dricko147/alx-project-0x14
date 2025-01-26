API Explorer: Mastering RESTful Connections
 Novice
 Weight: 1
 Project will start Jan 19, 2025 1:00 PM, must end by Jan 26, 2025 1:00 PM
 Checker was released at Jan 19, 2025 1:00 PM
 Manual QA review must be done (request it when you are done with the project)
 An auto review will be launched at the deadline
Quiz questions
Great! You've completed the quiz successfully! Keep going! (Show quiz)
Tasks
0. Reading API Documentation
mandatory
Objectives: To use an API right, you need to read and understand the API documentation. This will give you a clear outline of what is needed to successfully make an API request, while further manipulating the response object. Especially, in TypeScript, knowing the structure of the request and response object allows you to design types or interfaces.

Instructions:

Create a New Project Directory:
Create a new project repository named alx-project-0x14.

Create README.md:
Create a README.md file in the root directory of your project.

Review API Documentation:
Visit the MoviesDatabase API documentation and review the available endpoints and features.

Add API Overview:
In your README.md, add a heading using ## for the API overview. Summarize the key features of the API in your own words.

Add API Version:
Below the API overview heading, add another heading using ## for version and state the version from the API documentation.

List Available Endpoints:
Create a section titled ## Available Endpoints and list the main endpoints available in the API along with a brief description of each.

Describe Request and Response Format:
Add a section titled ## Request and Response Format detailing the structure of a typical request and the corresponding response object. Use examples from the documentation.

Authentication Requirements:
Create a section titled ## Authentication and describe how to authenticate your requests (e.g., API key, headers required).

Error Handling:
Include a section titled ## Error Handling where you explain common error responses from the API and how to handle them in your code.

Usage Limits and Best Practices:
Add a final section titled ## Usage Limits and Best Practices that outlines any usage limitations (e.g., rate limits) and recommendations for effectively using the API.

Repo:

GitHub repository: alx-project-0x14
File: README.md
1. Bootstrap MovieApp
mandatory
Objectives: To kickstart the development of your movie application using Next.js, you will set up a new project with TypeScript, ESLint, and Tailwind CSS. This foundational setup will help ensure your code is well-structured, maintainable, and styled efficiently from the beginning.

Instructions:

Create a New Next.js Project:
Open your terminal and run the following command to create a new Next.js app named alx-movie-app:
npx create-next-app@latest alx-movie-app --typescript --eslint --tailwind
Choose option No for the following
√ Would you like to use `src/` directory? ... No / Yes
√ Would you like to use App Router? (recommended) ... No / Yes

Choose option YES for the following
? Would you like to customize the default import alias (@/*)? » No / Yes

Navigate to Project Directory:
cd alx-movie-app
Setup your base directories

components/commons/Button.tsx

components/commons/Loading.tsx

components/commons/MovieCard.tsx

components/layouts/Header.tsx

components/layouts/Footer.tsx

components/layouts/Layout.tsx

components/layouts/Button.tsx

For each file create the Base functional component and export default at the end of the file

Install the following dependencies
npm install @fortawesome/react-fontawesome @fortawesome/free-brands-svg-icons @fortawesome/fontawesome-svg-core
Repo:

GitHub repository: alx-project-0x14
Directory: alx-movie-app
File: components/commons/Button.tsx, components/commons/Loading.tsx, components/commons/MovieCard.tsx, components/layouts/Header.tsx, components/layouts/Footer.tsx, components/layouts/Layout.tsx, components/layouts/Button.tsx, package.json
2. Set up Header, Footer, Layout and landing page
mandatory
Objectives: To create a cohesive user interface for your movie application, you’ll set up a consistent layout by implementing a header and footer. This will enhance navigation and provide a professional look to your app. Additionally, you’ll create a landing page to greet users.

Instructions:

Create Layout Component:

In the components/layout directory, create a new file named Layout.tsx. This component will wrap around your page content.

import { ComponentProps } from "@/interfaces";
import Header from "./Header";
import Footer from "./Footer";

const Layout: React.FC<ComponentProps> = ({ children }) => {
  return (
    <>
      <Header />
      <main className="min-h-screen">{children}</main>
      <Footer />
    </>
  )
}

export default Layout;
Create Header Component:

In the components/layout directory, create a file named Header.tsx.

import Link from "next/link"
import Button from "../commons/Button"

const Header: React.FC = () => {
  return (
    <header className="h-28 flex items-center bg-[#171D22] px-4 md:px-16 lg:px-44 text-white">
      <div className="flex items-center justify-between w-full">
        <h2 className="text-xl md:text-4xl font-semibold">Cine<span className="text-[#E2D609]">Seek</span></h2>
        <nav className="hidden md:flex flex-1 justify-center space-x-8">
          <Link href="/" className="hover:text-[#E2D609] px-4 md:px-8 text-xl transition-colors duration-300 font-semibold">Home</Link>
          <Link href="/movies" className="hover:text-[#E2D609] px-4 md:px-8 text-xl transition-colors duration-300 font-semibold">Movies</Link>
          <Link href="/contact" className="hover:text-[#E2D609] px-4 md:px-8 text-xl transition-colors duration-300 font-semibold">Contact</Link>
        </nav>
        <div className="flex md:hidden">
          <Button title="Sign in" />
        </div>
        <div className="hidden md:flex">
          <Button title="Sign in" />
        </div>
      </div>
    </header>

  )
}

export default Header
Create Footer Component:

In the components/layout directory, create a file named Footer.tsx.

import Link from "next/link";
import { FontAwesomeIcon } from "@fortawesome/react-fontawesome";
import { faTwitter, faFacebook, faInstagram } from "@fortawesome/free-brands-svg-icons";

const Footer: React.FC = () => {
  return (
    <footer className="bg-[#171D22] text-white py-10 px-6 md:px-10 lg:px-20">
      <div className="flex flex-col md:flex-row justify-between items-center w-full">
        {/* Footer Logo */}
        <h2 className="text-xl md:text-4xl font-semibold mb-4 md:mb-0">
          Cine<span className="text-[#E2D609]">Seek</span>
        </h2>

        <nav className="flex-1 flex justify-center space-x-6 mb-4 md:mb-0">
          <Link href="/" className="hover:text-[#E2D609] text-lg transition-colors duration-300">Home</Link>
          <Link href="/movies" className="hover:text-[#E2D609] text-lg transition-colors duration-300">Movies</Link>
          <Link href="/contact" className="hover:text-[#E2D609] text-lg transition-colors duration-300">Contact</Link>
          <Link href="/privacy" className="hover:text-[#E2D609] text-lg transition-colors duration-300">Privacy Policy</Link>
        </nav>

        <div className="flex space-x-4">
          <a href="https://twitter.com" target="_blank" rel="noopener noreferrer" className="hover:text-[#E2D609]">
            <FontAwesomeIcon icon={faTwitter} size="lg" />
          </a>
          <a href="https://facebook.com" target="_blank" rel="noopener noreferrer" className="hover:text-[#E2D609]">
            <FontAwesomeIcon icon={faFacebook} size="lg" />
          </a>
          <a href="https://instagram.com" target="_blank" rel="noopener noreferrer" className="hover:text-[#E2D609]">
            <FontAwesomeIcon icon={faInstagram} size="lg" />
          </a>
        </div>
      </div>

      <div className="mt-8 text-center text-sm text-gray-400">
        <p>&copy; 2024 CineSeek. All rights reserved.</p>
      </div>
    </footer>

  );
};

export default Footer;
Create Button Component:

In the components/commons directory, create a file named Button.tsx.

Replace the content with the following

import { ButtonProps } from "@/interfaces";

const Button: React.FC<ButtonProps> = ({ title, action }) => {
  return (
    <button onClick={action} className="px-8 py-2 border-2 border-[#E2D609] rounded-full hover:bg-[#E2D609] hover:text-black transition-colors duration-300">
      {title}
    </button>
  )
}

export default Button;
Create some interface

In the interfaces directory, create a file named index.ts.

Replace the content with the following

import { ReactNode } from "react";

export interface ComponentProps {
  children: ReactNode
}

export interface ButtonProps {
  title: string
  action?: () => void
}
Setup your layout:

In the pages directory, open the file named _app.tsx.

Replace the content with the following

import Layout from "@/components/layouts/Layout";
import "@/styles/globals.css";
import type { AppProps } from "next/app";

export default function App({ Component, pageProps }: AppProps) {
  return (
    <Layout>
      <Component {...pageProps} />
    </Layout>
  )
}

*Setup your landing page:

In the pages directory, open the file named index.tsx.

Replace the content with the following

import Button from "@/components/commons/Button";
import { useRouter } from "next/router";
const Home: React.FC = () => {
  const router = useRouter();

  return (
    <div className="bg-[#171D22] text-white">
      <section
        className="h-screen bg-cover bg-center"
        style={{
          backgroundImage:
            'url("https://themebeyond.com/html/movflx/img/bg/breadcrumb_bg.jpg")',
        }}
      >
        <div className="bg-black bg-opacity-50 h-full flex flex-col justify-center items-center text-center">
          <h1 className="text-5xl md:text-7xl font-bold mb-8">
            Discover Your Next Favorite{" "}
            <span className="text-[#E2D609]">Movie</span>
          </h1>
          <p className="text-lg md:text-2xl mb-8 max-w-2xl">
            Explore the latest blockbuster movies, critically acclaimed films,
            and your personal favorites – all in one place.
          </p>
          <Button
            title="Browse Movies"
            action={() => router.push("/movies", undefined, { shallow: false })}
          />
        </div>
      </section>

      <section className="py-16 px-8 md:px-44 bg-[#121018] text-center">
        <h2 className="text-3xl md:text-5xl font-semibold mb-8">
          Join CineSeek Now!
        </h2>
        <p className="text-lg md:text-2xl mb-12">
          Sign up today to get access to the latest movies, exclusive content,
          and personalized movie recommendations.
        </p>
        <Button title="Get Started" />
      </section>
    </div>
  );
};

export default Home;
Save and close your files
Run npm run dev from the terminal
From a tab in your browser type http://localhost:3000 to see the changes made.
Repo:

GitHub repository: alx-project-0x14
Directory: alx-movie-app
File: .components/commons/Button.tsx, components/layout/Header.tsx,components/layout/Footer.tsx, components/layout/Layout.tsx, pages/_app.tsx, pages/index.tsx
3. Add the movies pages to you project
mandatory
Objective: Create a dedicated movies section in your CineSeek application that allows users to view a list of movies and individual movie details.

Instructions:

Create the MovieCard Component:

Create a new file named MovieCard.tsx in your components/commons directory.

Replace the content with the following:

import { MovieProps } from "@/interfaces"
import Image from "next/image"

const MovieCard: React.FC<MovieProps> = ({ title, posterImage, releaseYear }) => {
  return (
    <div className="h-[563px]">
      <div>
        <Image className="h-[430px] w-full rounded-md hover:cursor-pointer" src={posterImage} width={100} height={100} alt={title} />

      </div>
      <div className="flex justify-between py-4">
        <p className="text-xl font-bold">{title}</p>
        <p className="text-xl text-[#E2D609]">{releaseYear}</p>
      </div>
    </div>
  )
}

export default MovieCard
Create the Loading Component:

Create a new file named Loading.tsxin your components/commons directory.

Replace the content with the following:

const Loading: React.FC = () => {
  return (
    <div className="fixed inset-0 bg-black bg-opacity-50 flex justify-center items-center z-50">
      <div className="bg-white bg-opacity-10 backdrop-blur-md rounded-lg p-8 flex flex-col justify-center items-center">
        <h1 className="text-4xl md:text-6xl font-semibold text-white mb-4 animate-pulse">
          Loading...
        </h1>
        <p className="text-lg text-gray-300">Please wait, we&apos;re getting next set of movies ready for you.</p>
      </div>
    </div>
  );
};

export default Loading;

Create the Movies Page:

Create a new file named index.tsx in your pages/movies directory.

Replace the content with the following

import Button from "@/components/commons/Button";
import Loading from "@/components/commons/Loading";
import MovieCard from "@/components/commons/MovieCard";
import { MoviesProps } from "@/interfaces";
import { useCallback, useEffect, useState } from "react";


interface MProps {
  movies: MoviesProps[]
}

const Movies: React.FC<MProps> = () => {

  const [page, setPage] = useState<number>(1)
  const [year, setYear] = useState<number | null>(null)
  const [genre, setGenre] = useState<string>("All")
  const [movies, setMovies] = useState<MoviesProps[]>([])
  const [loading, setLoading] = useState<boolean>(false)

 const fetchMovies = useCallback(async () => {
    setLoading(true)
    const response = await fetch('/api/fetch-movies', {
      method: 'POST',
      body: JSON.stringify({
        page,
        year, 
        genre: genre === "All" ? "" : genre
      }),
      headers: {
        'Content-Type': 'application/json; charset=utf-8'
      }
    })

    if (!response.ok) {
      setLoading(false)
      throw new Error("Something went wrong")
    }

    const data = await response.json()
    const results = data.movies
    console.log(results)
    setMovies(results)
    setLoading(false)
  }, [page, year, genre])


  useEffect(() => {
    fetchMovies()
  }, [fetchMovies])




  return (
    <div className="min-h-screen bg-[#110F17] text-white px-4 md:px-10 lg:px-44">
  <div className="py-16">
    <div className="flex flex-col md:flex-row justify-between mb-4 items-center space-x-0 md:space-x-4">
      <input
        type="text"
        placeholder="Search for a movie..."
        className="border-2 w-full md:w-96 border-[#E2D609] outline-none bg-transparent px-4 py-2 rounded-full text-white placeholder-gray-400"
      />

      <select
        onChange={(event: React.ChangeEvent<HTMLSelectElement>) => setYear(Number(event.target.value))}
        className="border-2 border-[#E2D609] outline-none bg-transparent px-4 md:px-8 py-2 mt-4 md:mt-0 rounded-full w-full md:w-auto"
      >
        <option value="">Select Year</option>
        {
          [2024, 2023, 2022, 2021, 2020, 2019].map((year: number) => (
            <option value={year} key={year}>{year}</option>
          ))
        }
      </select>
    </div>

    <p className="text-[#E2D609] text-xl mb-6 mt-6">Online streaming</p>
    <div className="flex flex-col md:flex-row items-center justify-between">
      <h1 className="text-lg md:text-6xl font-bold">{year} {genre} Movie List</h1>
      <div className="flex flex-wrap space-x-0 md:space-x-4 mt-4 md:mt-0">
        {
          ['All', 'Animation', 'Comedy', 'Fantasy'].map((genre: string, key: number) => (
            <Button title={genre} key={key} action={() => setGenre(genre)} />
          ))
        }
      </div>
    </div>

    {/* Movies output */}
    <div className="grid grid-cols-2 gap-4 md:grid-cols-3 lg:grid-cols-4 xl:grid-cols-6 mt-10">
      {
        movies?.map((movie: MoviesProps, key: number) => (
          <MovieCard
            title={movie?.titleText.text}
            posterImage={movie?.primaryImage?.url}
            releaseYear={movie?.releaseYear.year}
            key={key}
          />
        ))
      }
    </div>
    <div className="flex justify-end space-x-4 mt-6">
      <Button title="Previous" action={() => setPage(prev => prev > 1 ? prev - 1 : 1)} />
      <Button title="Next" action={() => setPage(page + 1)} />
    </div>
  </div>
  {
    loading && <Loading />
  }
</div>

  )
}


export default Movies;

Expand the interfaces to accommodate for the Movies:

Replace the content of interfaces/index.ts with the following:


import { ReactNode } from "react";

export interface ComponentProps {
  children: ReactNode
}

export interface ButtonProps {
  title: string
  action?: () => void
}

export interface MovieProps {
  id?: string
  posterImage: string
  releaseYear: string
  title: string
}

interface PrimaryImage {
  url: string
}

interface TitleText {
  text: string
}

interface ReleaseYear {
  year: string
}

export interface MoviesProps {
  id: string
  primaryImage: PrimaryImage
  titleText: TitleText
  releaseYear: ReleaseYear
}
Setup your local environment variables

Create the file .env.local under the root directory

Replace the content with the following:

MOVIE_API_KEY=PASTE_YOUR_API_KEY_HERE
Create the data fetching method

Create a new file named fetch-movies.ts in your pages/api directory.

Replace the content with the following


import { MoviesProps } from "@/interfaces";
import { NextApiRequest, NextApiResponse } from "next";
export default async function handler (request: NextApiRequest, response: NextApiResponse)  {

  if (request.method === "POST") {
    const { year, page, genre } = request.body;
    const date = new Date();
    const resp = await fetch(
      `https://moviesdatabase.p.rapidapi.com/titles?year=${
        year || date.getFullYear()
      }&sort=year.decr&limit=12&page=${page}&${genre && `genre=${genre}`}`,
      {
        headers: {
          "x-rapidapi-host": "moviesdatabase.p.rapidapi.com",
          "x-rapidapi-key": `${process.env.MOVIE_API_KEY}`,
        },
      }
    );

    if (!resp.ok) throw new Error("Failed to fetch movies");

    const moviesResponse = await resp.json();
    const movies: MoviesProps[] = moviesResponse.results;

    return response.status(200).json({
      movies,
    });
  } else {
    response.setHeader('Allow', ['POST']);
    response.status(405).end(`Method ${request.method} Not Allowed in here`);
  }
};
Save and close your files
Run npm run dev from the terminal
From a tab in your browser type http://localhost:3000 to see the changes made.
Repo:

GitHub repository: alx-project-0x14
Directory: alx-movie-app
File: components/commons/Loading.tsx, components/commons/MovieCard.tsx,pages/movies/index.tsx, interfaces/index.ts, pages/api/fetch-movies.ts, .gitignore
4. Manual Review
mandatory
Repo:

GitHub repository: alx-project-0x14