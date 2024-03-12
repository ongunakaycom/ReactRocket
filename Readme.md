# React on the Edge

React on the Edge is a project that leverages Vercel Edge Functions for server-side rendering (SSR) with React, similar to SvelteKit but using React instead. It utilizes esbuild for bundling, providing efficient and fast build times.

## Introduction

This project is designed for advanced usage and framework builders who want to explore the capabilities of Vercel Edge Functions combined with React. While Next.js Middleware and Vercel Edge Functions are recommended for most React applications with dynamic Edge capabilities, React on the Edge provides a low-level approach for those seeking deeper customization.

## Getting Started

To get started with React on the Edge, follow these steps:

1. Install dependencies using pnpm:

```bash
pnpm install
```

2. To build the project:

```bash
pnpm build
```

3. To run a local server:

```bash
pnpm start
```

4. For streaming (renderToStream) instead of renderToString, use the following command:

```bash
USE_STREAMS=1 pnpm build
```

## Architecture

The project's architecture is as follows:

- `util/build.mjs`: Implements the build process using esbuild to bundle `src/app` into an Edge Function.
- `util/start.mjs`: Implements a local server using the `edge-runtime` package to locally run the build outputs.

## Developing

Due to the absence of a dev server, you can use `watchexec` as a replacement. Install `watchexec` using:

```bash
brew install watchexec
```

Then run the following command to watch for changes and rebuild/start the server:

```bash
watchexec -c -r --no-meta 'node util/build.mjs; node util/start.mjs'
```

## Conclusion

React on the Edge offers a unique approach to server-side rendering with React, leveraging Vercel's powerful Edge Functions. It provides flexibility and control for developers looking to build advanced applications with React while harnessing the benefits of edge computing. Explore the possibilities and unleash the full potential of React on the edge!
