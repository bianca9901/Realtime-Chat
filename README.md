## Note

This application uses Google OAuth for authentication. Due to the nature of this authentication mechanism, only users with email addresses I manually add to the authentication configuration can access the application. Therefore, a deployed version of the application is not provided.

However, you can still run the application locally for development purposes. Follow the steps below to set it up. Note that if you plan to deploy the application yourself, you will need to configure Google OAuth accordingly.

## How To Use

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

### **3. Set Up Accounts and Get keys for Your Environment variables**

**First, you will need an account on Google, Upstash and Pusher. I will guide you through the next steps:**

In **Google Console**, follow these steps:

**
1. Sign in to the Google Cloud Console.
   
2. Create a new project and navigate to your project's APIs & Services

3. In the "OAuth consent screen" tab, add your App domain:
This is the domain where your application is hosted. Google only allows apps using OAuth to use authorized domains for security reasons.

4. In the "Test users" section, add at least two users:
This is to ensure you can test your application with different user accounts.

5. Navigate to the credentials tab.
   
6. Choose the appropriate user type:
If you select "External", you'll need to manually add the users who can access your app. Alternatively, you can choose "Internal" if you prefer.
   
9. Add the Authorized JavaScript origins:
This should include http://localhost:3000 for requests from a browser.

11. Add the Authorized redirect URIs:
For requests from a web server, include http://localhost:3000/api/auth/callback/google.

13. Copy your Client ID and Client Secret:
Finally, on the left side of the screen, you'll find your Client ID and Client Secret. Copy these credentials for later use in your application.

**


On **Upstash**, follow these steps:

--

On **Pusher**, follow these steps:

--

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
UPSTASH_REDIS_REST_URL= // URL for accessing the Upstash Redis database.

UPSTASH_REDIS_REST_TOKEN= // Token for authentication with the Upstash Redis database.

GOOGLE_CLIENT_ID= // Client ID obtained from the Google Developer Console for OAuth authentication.

GOOGLE_CLIENT_SECRET= // Client secret obtained from the Google Developer Console for OAuth authentication.

NEXTAUTH_SECRET= // Secret used by NextAuth.js for session encryption (choose your own secret password).

PUSHER_APP_ID= //  ID of your Pusher application.

NEXT_PUBLIC_PUSHER_APP_KEY= // Public key of your Pusher application.

PUSHER_APP_SECRET= //  Secret key of your Pusher application.
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
