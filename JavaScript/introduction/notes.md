# Introduction to JavaScript

## What is JS?

- JavaScript was initially created to “make web pages alive”.
- The programs in this language are called scripts. They can be written right in a web page’s HTML and run automatically as the page loads.
- Scripts are provided and executed as plain text. They don’t need special preparation or compilation to run.

> Great resource: [here](https://javascript.info/)

## How to run?

- By docker:

    ```bash
    # Docker has specific installation instructions for each operating system.
    # Please refer to the official documentation at https://docker.com/get-started/

    # Pull the Node.js Docker image:
    docker pull node:22-alpine

    # Create a Node.js container and start a Shell session:
    docker run -it --rm --entrypoint sh node:22-alpine

    # Verify the Node.js version:
    node -v # Should print "v22.19.0".

    # Verify npm version:
    npm -v # Should print "10.9.3".

    # To start node interpreter
    node 
    ```

- Hello world:

    ```js
    console.log("hello world")
    ```
