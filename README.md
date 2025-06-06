# T3Chat Electron App

A simple Electron application that launches [https://t3.chat](https://t3.chat) in a dedicated, Chromium-based window.

## Prerequisites

Before you begin, ensure you have the following installed:
*   [Node.js](https://nodejs.org/) (which includes npm)
*   [PNPM](https://pnpm.io/) (used in place of npm, but npm will still work)

What is election? I've created a brief explainer here: https://youtu.be/wmyMKbUoC2w

## Setup and Installation

1.  **Clone the repository (if applicable) or download the files.**
    If this project is part of a larger repository, ensure you have the `t3chat-electron-app` directory.

2.  **Navigate to the application directory:**
    ```bash
    cd path/to/t3chat-electron-app
    ```

3.  **Install dependencies:**
    Open your terminal in the `t3chat-electron-app` directory and run:
    ```bash
    pnpm  install
    ```
    This command will download and install Electron and any other necessary packages defined in `package.json`.

## Running the Application

Once the dependencies are installed, you can start the application using:

```bash
pnpm start
```

This will launch the Electron application, and a window will open displaying the t3.chat website.

## Development

The main files for this application are:

*   **`main.js`**: This is the primary script that Electron runs. It's responsible for creating the browser window and loading the URL. Any modifications to the application's main process, window behavior, or Node.js integrations would typically start here.
*   **`package.json`**: This file defines the project's metadata, dependencies, and scripts. The `electron` dependency is crucial, and the `start` script (`electron .`) tells Electron to run the current directory.

### To make changes:

1.  Modify `main.js` or other project files as needed.
2.  If you've stopped the application, restart it with `pnpm start` to see your changes.
3.  You can uncomment `win.webContents.openDevTools();` in `main.js` to open the Chromium Developer Tools for debugging the renderer process (the web page content).
4. Replace `win.loadURL("https://t3.chat");` in `main.js` with any URL you want to embed as a standalone desktop app
5. Replace the name of the project in the `package.json` to your applications prefered name

## Building the Application for macOS

This project uses `electron-builder` to package the application. Configuration for the build process is located in the `build` section of the `package.json` file.

### Prerequisites for Building

*   Ensure all dependencies are installed:
    ```bash
    pnpm install
    ```
    This will also install `electron-builder` which is listed under `devDependencies`.

### Build Command

To build the application for macOS (which will generate a `.dmg` file), run the following command in the `t3chat-electron-app` directory:

```bash
pnpm run build
```

To build for other/multiple platforms you'll need to update the `build` config in `package.json` according to the electron.js documents

### Output

After a successful build, you will find the distributable file (e.g., `T3Chat Electron App-1.0.0.dmg`) in the `t3chat-electron-app/dist` directory.

This `.dmg` file can be distributed and installed on macOS systems.

## License

ISC
