# Realtime-Chat

## Features

**Instant real-time functionality:** powered by Upstash Redis, for immediate updates and interactions within the application.

**Real-time chat and friend requests:** powered by Pusher for used for efficient social interactions.

**Comprehensive friend system** enabling users to manage friend requests (add, accept, or deny).

**Database queries** powered by Redis, optimizing performance.

**Responsive user interface** designed with Tailwind CSS for consistent experiences across various devices.

**Route protection** mechanisms to secure sensitive application areas.

**User authentication** through integration with Google Authentication.

## Note

This application uses Google OAuth for authentication. Due to the nature of this authentication mechanism, only users with email addresses I manually add to the authentication configuration can use the features of the application. Therefore, a deployed version of the application is not provided.

However, you can still run the application locally for development purposes. Follow the steps below to set it up. Note that if you plan to deploy the application yourself, you will need to configure Google OAuth accordingly.

## How To Use In Local Development

Follow these steps to get started with the project:

### **1. Clone the Repository**

First, clone the repository to your local machine using the following command:

```
git clone https://github.com/bianca9901/Realtime-Chat.git

```

### **2. Install Dependencies**

Navigate into the project directory and install the dependencies using npm or yarn:

```
cd realtime-chat-app

```

```
npm install

```

or

```
yarn install
```

### **3. Set up Accounts and get keys for your Environment Variables**

**First, you will need an account on Google, Upstash and Pusher. I will guide you through the next steps:**


On **Google Console**, follow these steps:

1. Sign in to [Google Cloud Console.](https://console.cloud.google.com/)
2. Click the "Select new Project" button and then select "Create a new project."
3. Name your project.
4. Click on the hamburger menu on the left and navigate to APIs & Services.
5. Click on the "OAuth consent screen" tab within the hamburger menu, and choose "External." Once selected, click on the "Create" button.
6. Provide a name for your app and your email in the App Information section.
7. Scroll down to the App domain, and in the Application homepage text field, add http://localhost:3000
8. Scroll further down to the Developer contact information and add your email address.
9. Click on "Save and Continue."
10. In the Scopes section, you can scroll to the bottom without filling in anything and click on "Save and Continue."
11. In the Test users section, you will need to add at least two Google accounts so that you can later test the features of the Realtime-Chat-App. Then, click on "Save and Continue."
12. Next, navigate to the "Credentials" section within the hamburger menu on the left. Click on "Create Credentials."
13. From the dropdown menu, select "OAuth client ID."
14. In the Application type dropdown, select "Web Application."
15. In the Authorized JavaScript origins section, add http://localhost:3000
16. In the Authorized redirect URIs section, add http://localhost:3000/api/auth/callback/google
17. Click on "Create," and then in the popup, you will see your Client ID and Client secret. Make sure to save these keys somewhere safe.


On **Upstash**, follow these steps:

1. Sign in to [Upstash.](https://upstash.com/)
2. Click on "Create database," select a name, choose your closest region, and then click "Create."
3. In the "Details" tab, scroll down to the REST API section, and copy your UPSTASH_REDIS_REST_URL and UPSTASH_REDIS_REST_TOKEN. Ensure to save them somewhere safe.


On **Pusher**, follow these steps:

1. Sign in to [Pusher.](https://pusher.com/)
2. Click on the "Get started" button inside the Channels box.
3. Name your app, select a cluster, and then click the "Create app" button.
4. In the menu on the left, navigate to "App keys," and copy all the keys (app_id, key, secret) you dont need to copy the cluster.
5. In the realtime-chat-app, navigate to src/lib/pusher.ts, and change the two clusters from "eu" to your region if you have a different region than I. Otherwise, you can skip this step.


**Environment Variables**

Create `.env.local` File In The Root Directory Of Your Project:

```
cd realtime-chat-app
```

```
touch .env.local
```

**Add all your secrets next to these variables:**

```
GOOGLE_CLIENT_ID= // Place the Client ID from Google Developer Console.

GOOGLE_CLIENT_SECRET= // Place the Client secret from Google Developer Console.

UPSTASH_REDIS_REST_URL= // Place the URL from Upstash Redis database.

UPSTASH_REDIS_REST_TOKEN= // Place the Token from Upstash Redis database.

PUSHER_APP_ID= //  Place the "app_id" from Pusher.

NEXT_PUBLIC_PUSHER_APP_KEY= // Place the "key" from Pusher.

PUSHER_APP_SECRET= //  Place the "secret" from Pusher.

NEXTAUTH_SECRET= // Secret used by NextAuth.js for session encryption (choose your own secret password).
```

### **4. Start the Development Server**

Once the dependencies are installed and environment variables are set up, you can start the development server:

```
npm run dev

```

or

```
yarn dev

```

This command will start the development server and your project will be accessible at **`http://localhost:3000`** by default.

### **5. Explore and Enjoy!**

You're all set! explore the project, interact with its features, and enjoy using it. If you encounter any issues or have feedback, feel free to open an issue on GitHub.

## Technologies Used

- **TypeScript**: A typed superset of JavaScript that compiles to plain JavaScript. [Learn more](https://www.typescriptlang.org/)
- **Next.js**: A React framework for building server-side rendered (SSR) and statically generated (SSG) web applications. [Learn more](https://nextjs.org/)
- **React**: A JavaScript library for building user interfaces. [Learn more](https://reactjs.org/)
- **Tailwind CSS**: A utility-first CSS framework for quickly styling web applications. [Learn more](https://tailwindcss.com/)
- **React Hot Toast**: A toast notification library for React applications. [Learn more](https://react-hot-toast.com/)
- **ESLint**: A tool for identifying and reporting on patterns found in ECMAScript/JavaScript code. [Learn more](https://eslint.org/)
- **Vercel:** A cloud platform for static sites and serverless functions, used for hosting the project. [Learn more](https://vercel.com/)
- **GitHub:** Repository hosting and version control. [Learn more](https://github.com/)
- **Git:** Version control. [Learn more](https://git-scm.com/)
- **Headlessui/react**: A library for building accessible components in React. [Learn more](https://headlessui.dev/)
- **Hookform/resolvers**: Resolvers for React Hook Form. [Learn more](https://www.npmjs.com/package/@hookform/resolvers)
- **Next-auth/upstash-redis-adapter**: Adapter for using Upstash Redis with NextAuth. [Learn more](https://authjs.dev/reference/adapter/upstash-redis)
- **Tailwindcss/forms**: Tailwind CSS plugin for styling form elements. [Learn more](https://tailwindcss.com/docs/plugins#forms)
- **Upstash/redis**: Redis client for Node.js. [Learn more](https://www.npmjs.com/package/@upstash/redis)
- **Axios**: Promise-based HTTP client for the browser and Node.js. [Learn more](https://axios-http.com/)
- **Class-variance-authority**: Library for class variance authority. [Learn more](https://www.npmjs.com/package/class-variance-authority)
- **Clsx**: A utility for constructing className strings conditionally. [Learn more](https://www.npmjs.com/package/clsx)
- **Date-fns**: Date utility library. [Learn more](https://date-fns.org/)
- **Encoding**: Solution for creating and parsing everything from binary to ASCII and Unicode. [Learn more](https://www.npmjs.com/package/encoding)
- **Lucide-react**: Icons for React. [Learn more](https://lucide.dev/)
- **Nanoid**: A secure URL-friendly unique string ID generator for JavaScript. [Learn more](https://www.npmjs.com/package/nanoid)
- **Next-auth**: Authentication for Next.js applications. [Learn more](https://next-auth.js.org/)
- **Pusher**: A Node.js client for Pusher Channels. [Learn more](https://pusher.com/)
- **Pusher-js**: JavaScript library for Pusher Channels. [Learn more](https://github.com/pusher/pusher-js)
- **React-hook-form**: For forms with easy-to-use validation. [Learn more](https://react-hook-form.com/)
- **React-loading-skeleton**: Creates loading placeholders for the project. [Learn more](https://www.npmjs.com/package/react-loading-skeleton)
- **React-textarea-autosize**: Textarea component for React which grows with content. [Learn more](https://www.npmjs.com/package/react-textarea-autosize)
- **Tailwind-merge**: Merge Tailwind CSS classes together. [Learn more](https://www.npmjs.com/package/tailwind-merge)
- **Zod**: TypeScript-first schema declaration and validation library. [Learn more](https://github.com/colinhacks/zod)
- **Google OAuth API**: Google's OAuth service for authentication and authorization. [Learn more](https://developers.google.com/identity/protocols/oauth2)
