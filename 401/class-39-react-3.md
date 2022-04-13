# React 3 - Next.js and React Context

[Reading for Next.js](https://nextjs.org/learn/basics/assets-metadata-css)

# Next.js - Assets, Metadata, and CSS

Next.js can serve static assets, like images, under the top-level public directory. Files inside public can be referenced from the root of the application similar to pages.

### Unoptimized Image

With regular HTML, you would add your profile picture as follows:

```
<img src="/images/profile.jpg" alt="Your Name" />
```

However, this means you have to manually handle:

- Ensuring your image is responsive on different screen sizes
- Optimizing your images with a third-party tool or library
- Only loading images when they enter the viewport

### Image Component and Image Optimization

`next/image` is an extension of the HTML `<img>` element, evolved for the modern web.

Example:

```
import Image from 'next/image'

const YourComponent = () => (
  <Image
    src="/images/profile.jpg" // Route of the image file
    height={144} // Desired size with correct aspect ratio
    width={144} // Desired size with correct aspect ratio
    alt="Your Name"
  />
)
```

### Metadata

What if we wanted to modify the metadata of the page, such as the `<title>` HTML tag?

`<title>` is part of the `<head>` HTML tag, so let's dive into how we can modify the `<head>` tag in a Next.js page.

Open pages/index.js in your editor and find the following lines:

```
<Head>
  <title>Create Next App</title>
  <link rel="icon" href="/favicon.ico" />
</Head>
```

### Third-Party JavaScript

Third-party JavaScript refers to any scripts that are added from a third-party source.

Usually, third-party scripts are included in order to introduce newer functionality into a site that does not need to be written from scratch, such as analytics, ads, and customer support widgets.

### Adding Third-Party JavaScript

```
<Head>
  <title>First Post</title>
  <script src="https://connect.facebook.net/en_US/sdk.js" />
</Head>
```

### Using the Script Component

```
import Script from 'next/script'
```

Now, update the FirstPost component to include the Script component:

```
export default function FirstPost() {
  return (
    <>
      <Head>
        <title>First Post</title>
      </Head>
      <Script
        src="https://connect.facebook.net/en_US/sdk.js"
        strategy="lazyOnload"
        onLoad={() =>
          console.log(`script loaded correctly, window.FB has been populated`)
        }
      />
      <h1>First Post</h1>
      <h2>
        <Link href="/">
          <a>Back to home</a>
        </Link>
      </h2>
    </>
  )
}
```

- `strategy` controls when the third-party script should load. A value of `lazyOnload` tells Next.js to load this particular script lazily during browser idle time
- `onLoad` is used to run any JavaScript code immediately after the script has finished loading. In this example, we log a message to the console that mentions that the script has loaded correctly

### CSS Styling

```
<style jsx>{`
  …
`}</style>
```

This page is using a library called `styled-jsx`. It’s a “CSS-in-JS” library — it lets you write CSS within a React component, and the CSS styles will be scoped (other components won’t be affected).

# React Context

React context allows us to share data `(state)` across our components more easily.

### When should React context be used?

These types of data include:

- Theme data (like dark or light mode)
- User data (the currently authenticated user)
- Location-specific data (like user language or locale)

Data should be placed on React context that does not need to be updated often.

### What problems does React context solve?

React context helps us avoid the problem of props drilling.

**Props drilling** is a term to describe when you pass props down multiple levels to a nested component, through components that don't need it.

Example:

```
export default function App({ theme }) {
  return (
    <>
      <Header theme={theme} />
      <Main theme={theme} />
      <Sidebar theme={theme} />
      <Footer theme={theme} />
    </>
  );
}

function Header({ theme }) {
  return (
    <>
      <User theme={theme} />
      <Login theme={theme} />
      <Menu theme={theme} />
    </>
  );
}
```

The `Header` component doesn't need `theme` other than to pass it down to its child component. In other words, it would be better for `User` , `Login` and `Menu` to consume the `theme` data directly.

### How do I use React context?

There are four steps to using React context:

1. Create context using the createContext method.
2. Take your created context and wrap the context provider around your component tree.
3. Put any value you like on your context provider using the value prop.
4. Read that value within any component by using the context consumer.

Example:

```
import React from 'react';

export const UserContext = React.createContext();

export default function App() {
  return (
    <UserContext.Provider value="Reed">
      <User />
    </UserContext.Provider>
  )
}

function User() {
  return (
    <UserContext.Consumer>
      {value => <h1>{value}</h1>}
      {/* prints: Reed */}
    </UserContext.Consumer>
  )
}
```

### What is the useContext hook?

Looking at the example above, the render props pattern for consuming context may look a bit strange.

Instead of using render props, we can pass the entire context object to React.useContext() to consume context at the top of our component.

Here is the example above using the useContext hook:

```
import React from 'react';

export const UserContext = React.createContext();

export default function App() {
  return (
    <UserContext.Provider value="Reed">
      <User />
    </UserContext.Provider>
  )
}

function User() {
  const value = React.useContext(UserContext);

  return <h1>{value}</h1>;
}
```
