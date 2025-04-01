# Take-Home Programming Test: React & Next.js UI Developer

## Introduction

This take-home test is designed to help us understand your approach to building web applications using React and Next.js.

We estimate this task should take approximately **4-7 hours** of focused work. Please don't feel pressured to over-engineer; focus on clean, functional code that meets the requirements and demonstrates your understanding of the core concepts.

## Goal

Build a simple web application that allows users to browse a list of items (e.g., blog posts, products, characters) fetched from a public API and view details for a selected item.

## Scenario: Simple Item Browser

You will create a small Next.js application that displays a list of items fetched from a public API. Users should be able to click on an item to view its details on a separate page.

## Choose ONE Public API

Select **one** of the following public APIs to use for this project:

1.  **JSONPlaceholder - Posts:**
    *   List Endpoint: `https://jsonplaceholder.typicode.com/posts`
    *   Detail Endpoint: `https://jsonplaceholder.typicode.com/posts/:id`
2.  **Rick and Morty API - Characters:**
    *   List Endpoint: `https://rickandmortyapi.com/api/character` (Supports pagination via `?page=X`)
    *   Detail Endpoint: `https://rickandmortyapi.com/api/character/:id`
3.  **PokéAPI - Pokémon:**
    *   List Endpoint: `https://pokeapi.co/api/v2/pokemon?limit=20&offset=0` (Supports pagination via `limit` and `offset`)
    *   Detail Endpoint: `https://pokeapi.co/api/v2/pokemon/:name_or_id`

*You are free to use another simple, free, public API if you prefer, but please state which one you used clearly in your submission README.*

## Core Requirements

1.  **Project Setup:**
    *   Initialize a new Next.js project using `create-next-app`.
    *   Use TypeScript (preferred) or JavaScript.
2.  **List Page (`/` or `/items`):**
    *   Fetch and display a list of items from your chosen API.
    *   For each item, display at least its name/title.
    *   Implement basic loading and error states while fetching data.
    *   Make each item in the list clickable, linking to its corresponding detail page.
    *   Include a simple text input field above the list that allows users to **filter the displayed items *client-side*** based on their name/title. Ensure filtering is reasonably efficient.
    *   Use an appropriate Next.js data fetching method (`getStaticProps`, `getServerSideProps`, or client-side fetching with SWR/React Query/useEffect). **Justify your choice briefly in your README**, specifically addressing the trade-offs regarding **SEO, initial load performance, and data freshness** for this list view.
3.  **Detail Page (`/items/[id]` or similar dynamic route):**
    *   Create a dynamic route that displays detailed information for a single item, fetched using its unique identifier (ID or name).
    *   Display more details than shown on the list page (e.g., body/content for posts, status/species for characters, abilities/types for Pokémon).
    *   Handle cases where the item ID is invalid or the fetch fails gracefully.
    *   Use an appropriate Next.js data fetching method for this page. **Justify your choice briefly in your README.**
        *   If using `getStaticProps` with `getStaticPaths`, explain how you handled potential **build times** if there were thousands of items and discuss the `fallback` option you chose (`true`, `false`, or `'blocking'`) and its implications.
        *   If using `getServerSideProps`, discuss the **performance impact** on the server.
4.  **Styling:**
    *   Apply basic styling to make the application presentable.
    *   You can use any method you prefer (CSS Modules, Tailwind CSS, Styled Components, Emotion, plain CSS).
    *   The application should be responsive and usable on mobile devices.
5.  **Code Quality:**
    *   Write clean, readable, and maintainable code.
    *   Structure your components logically.
    *   Use functional components and Hooks.
6.  **Version Control:**
    *   Use Git for version control throughout your development process.
    *   Include a sensible `.gitignore` file.

## Bonus Requirements (Optional)

Choose any you find interesting - completing these can showcase additional skills but focus on the core requirements first.

*   **Pagination or Infinite Scroll:** Implement pagination or infinite scrolling on the list page if the API supports it.
*   **Advanced Search/Filtering:** Enhance the filtering (e.g., server-side filtering if feasible, filtering by multiple fields).
*   **State Management (Favorites):** Implement a "favorites" feature. Allow users to mark/unmark items as favorites, persisting this state using `localStorage` or Context API/State Management Library.
*   **Testing:** Write basic unit/integration tests for one or two key components or utility functions using Jest and React Testing Library.
*   **Accessibility (a11y):** Ensure basic accessibility standards are met (semantic HTML, sufficient color contrast, alt tags for images if applicable, keyboard navigation).
*   **API Route:** Create a simple Next.js API route (`/api/...`) that perhaps proxies one of the public API requests or serves some mock data used elsewhere in the app.
*   **Deployment:** Deploy your application to Vercel (or another platform) and provide the link in your README.

## Deliverables

1.  **A link to a Git repository** (e.g., GitHub, GitLab) containing your source code. Ensure the repository is public or grant access to the hiring team ([Provide GitHub Handles/Emails if needed]).
2.  **The repository MUST include a `README.md` file (this file!) detailing:**
    *   **Setup Instructions:** Clear instructions on how to install dependencies (`npm install` or `yarn install`) and run the project locally (`npm run dev` or `yarn dev`).
    *   **API Choice:** Which public API you chose to use.
    *   **Data Fetching Justifications:** Your brief justifications for the Next.js data fetching methods chosen for both the List and Detail pages, addressing the points mentioned in the Core Requirements.
    *   **Assumptions/Challenges:** Any assumptions made or significant challenges faced during development.
    *   **Bonus Features:** Mention which, if any, bonus features you implemented.
    *   **Deployment Link:** (Optional) Link to the live deployment if you completed that bonus task.
    *   **Discussion Questions:** Brief answers to the following questions:
        *   **a) Frequent Data Updates:** Imagine the data for a specific item on the Detail Page could be updated frequently *after* the site has been built. How would you modify your data fetching strategy for the Detail Page to ensure users see reasonably fresh data without sacrificing all performance benefits? Briefly describe the Next.js feature(s) (like ISR or client-side fetching) you might use and why.
        *   **b) Rendering Performance:** Consider your List Page component. If the list grew to hundreds of items, what are potential React rendering bottlenecks? Briefly describe one or two techniques (e.g., specific React hooks or patterns) you could apply *within the component itself* to mitigate these, assuming virtualization/windowing is not yet implemented.
        *   **c) Custom Hook Usage:** Did you use custom hooks? If yes, briefly explain the main benefit. If not, describe a piece of logic that *could* have been extracted into a custom hook and why that might (or might not) have been beneficial.
        *   **d) State Management Trade-offs (If Favorites Bonus Implemented):** If you used Context API for the 'Favorites' feature, what are its potential downsides in larger apps? What's one alternative approach you might consider and why? (If not implemented, answer hypothetically).
        *   **e) Next.js Page Lifecycle:** Briefly describe the request lifecycle for BOTH your List Page and Detail Page. Mention where code executes (server/client/build time) for data fetching and rendering based on the strategies you chose.

## Evaluation Criteria

We will evaluate your submission based on:

*   **Functionality:** Does the application meet all core requirements and work as expected?
*   **Code Quality:** Is the code clean, well-structured, readable, and maintainable?
*   **React/Next.js Concepts:** Does the submission demonstrate a good understanding of React hooks, component composition, Next.js routing, data fetching patterns (SSG, SSR, CSR, ISR), and their trade-offs?
*   **Problem Solving & Justification:** How did you approach the requirements? Are your choices (e.g., data fetching) well-justified in the README? Do your answers to the discussion questions demonstrate depth of understanding?
*   **Styling & Responsiveness:** Is the UI visually presentable and functional on different screen sizes?
*   **Bonus Points:** Extra consideration for well-implemented bonus features demonstrating broader skills.

## Support

If you have **clarifying questions** about the requirements themselves, please reach out to [vikash@makeit.sg]. However, we cannot provide assistance with implementing the solution.
