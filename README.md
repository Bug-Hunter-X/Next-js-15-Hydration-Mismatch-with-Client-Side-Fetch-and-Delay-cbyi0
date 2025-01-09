# Next.js 15 Hydration Mismatch with Client-Side Fetch and Delay

This repository demonstrates a hydration mismatch issue in Next.js 15 when using `fetch` within a client component that experiences a delay before resolving. The problem occurs when the client-side fetch resolves after the server-side render, leading to inconsistencies and a blank screen or error.

## Reproducing the Issue

1. Clone this repository.
2. Run `npm install`.
3. Run `npm run dev`.
4. Navigate to the `/about` page.

You'll initially see a loading message. However, if the API simulation delay (currently set to 2 seconds) is sufficient, the page will stay blank or throw a hydration mismatch error. 

## Solution

The solution involves using a loading state and conditional rendering to gracefully handle the asynchronous data fetching.  This prevents rendering the component before the data is available, avoiding the hydration mismatch.
