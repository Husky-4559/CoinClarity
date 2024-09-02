# CoinClarity

CoinClarity is a full-stack application for managing and displaying financial records. The frontend is built using React, React Router, and TypeScript, integrated with Clerk for user authentication and management. The backend is developed using Node.js, Express, and MongoDB with Mongoose. The entire project is structured as a monorepo with separate `client` and `server` directories.

https://coinclarity-1.onrender.com

## Why I Built This Application

As the world becomes increasingly digitized, managing personal finances has never been more critical. The ease of digital transactions has made it simpler for money to flow out of our accounts, sometimes without us even realizing it. This can lead to overspending, financial stress, and difficulty in achieving long-term financial goals.

I built CoinClarity to address these challenges. This application is designed to empower individuals to take control of their financial lives by providing a clear, detailed view of their spending habits. With CoinClarity, users can track their expenses, create and manage budgets, and ultimately make informed financial decisions that lead to better financial health.

## The Importance of Financial Expense Tracking

Tracking expenses is a vital practice for anyone looking to maintain or improve their financial stability. It helps individuals understand where their money is going, identify unnecessary expenditures, and ensure they are on track to meet their financial goals. In a world where financial literacy is becoming increasingly important, tools like CoinClarity provide the transparency and control necessary to build a secure financial future.

## Table of Contents

- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Client](#client)
  - [Environment Variables](#environment-variables-client)
  - [Styling](#styling-client)
- [Server](#server)
  - [Environment Variables](#environment-variables-server)
  - [Database Schema](#database-schema)
- [Scripts](#scripts)
- [Linting](#linting)
- [License](#license)

## Project Structure

```plaintext
CoinClarity/
├── client/
│   ├── node_modules/                  # Project dependencies
│   ├── public/                        # Static assets served directly by the server
│   ├── src/                           # Source code for the client-side application
│   │   ├── assets/                    # Images, fonts, and other static assets
│   │   ├── contexts/                  # React Contexts for global state management
│   │   ├── pages/                     # Page-level components
│   │   ├── App.css                    # Global styles for the app
│   │   ├── App.tsx                    # Root component for the React app
│   │   ├── index.css                  # Additional global styles
│   │   ├── index.tsx                  # Entry point of the React app
│   │   ├── main.tsx                   # Main entry for Vite
│   │   └── vite-env.d.ts              # TypeScript definitions for Vite
│   ├── .env.local                     # Local environment variables (ignored in Git)
│   ├── .gitignore                     # Files and directories to be ignored by Git
│   ├── eslint.config.js               # ESLint configuration for code linting
│   ├── index.html                     # HTML template for the app
│   ├── package.json                   # Project metadata and dependencies
│   ├── README.md                      # Documentation for the client-side project
│   ├── tsconfig.app.json              # TypeScript configuration for the client-side app
│   ├── tsconfig.json                  # Root TypeScript configuration
│   ├── tsconfig.node.json             # TypeScript configuration for Node-related scripts
│   ├── vite.config.ts                 # Vite configuration for development and build
│   └── yarn.lock                      # Yarn lockfile for consistent dependency versions
├── server/
│   ├── build/                         # Compiled output of the server-side code
│   ├── node_modules/                  # Project dependencies
│   ├── src/                           # Source code for the server-side application
│   │   ├── routes/                    # Express route handlers
│   │   ├── schema/                    # Mongoose schemas
│   │   ├── index.ts                   # Entry point of the server application
│   ├── .env                           # Environment variables (ignored in Git)
│   ├── .gitignore                     # Files and directories to be ignored by Git
│   ├── package.json                   # Project metadata and dependencies
│   ├── README.md                      # Documentation for the server-side project
│   ├── tsconfig.json                  # TypeScript configuration for the server-side app
│   └── yarn.lock                      # Yarn lockfile for consistent dependency versions
└── README.md                          # Root-level documentation for the entire project

```

## Installation

1. **Clone the repository:**

   ```bash
   git clone https://github.com/Husky-4559/CoinClarity.git
   cd CoinClarity

   ```

2. **Install dependencies for both client and server:**

- cd client
- yarn install
- cd ../server
- yarn install

3. **Set up the environment variables:**

   Both the client and server have their respective environment variables. Create .env files in each directory with the required variables.

## Usage

Development

To start both the client and server in development mode:

- Start The server
  [cd server
  yarn dev]
- Start The client. Open a new terminal window/tab and run: [cd client
  yarn dev]

This will start both the backend API and the frontend application locally.

Production

1. **_Build The Server_**:

- cd server
  yarn build

2. **_Build The Client_**:

- cd client
  yarn build

You can then serve the built client using any static file server, and the built server files can be deployed on a Node.js server.

3. **_Preview The Client Build_**:

- cd client
  yarn preview

## Client

The client is a react application with the following features:
Environment Variables (Client)

    •	VITE_API_URL: The URL for the backend API.
    •	VITE_CLERK_PUBLISHABLE_KEY: The Clerk publishable key for authentication.

Styling (Client)

The client uses CSS for styling, with several CSS files:

    •	index.css: Global styles applied throughout the application.
    •	App.css: Styles specific to the App component and its children.
    •	financial-record.css: Styles specific to the financial record components.

## Server

The server is built with Node.js and Express, connected to a MongoDB database using Mongoose.

Environment Variables (Server)

    •	MONGO_URI: The connection string for your MongoDB database.
    •	PORT: The port on which the server will run.

Database Schema

The financial record schema defines the structure of the financial records stored in the MongoDB databse.

- Financial Record Schema:
  +------------------+

        | FinancialRecord  |

        +------------------+

        | userId           |

        | date             |

        | description      |

        | amount           |

        | category         |

        | paymentMethod    |

        +------------------+

FinancialRecord:

- userId: String (Not Null)
- date: Date (Not Null)
- description: String (Not Null)
- amount: Number (Not Null)
- category: String (Not Null)
- paymentMethod: String (Not Null)

## Scripts

Client

    •	yarn dev: Starts the Vite development server.
    •	yarn build: Builds the app for production and TypeScript compilation.
    •	yarn lint: Runs ESLint to check for code quality.
    •	yarn preview: Previews the production build locally.

Server

    •	yarn start: Starts the server from the compiled files in the build directory.
    •	yarn build: Compiles the TypeScript files into JavaScript.
    •	yarn dev: Starts the server in development mode with nodemon.
    •	yarn lint: Runs ESLint to check for code quality.

## Linting

ESLint is set up to ensure code quality in both the client and server. To run ESLint, use:

- yarn lint

## License

This project is licensed under the MIT License.
