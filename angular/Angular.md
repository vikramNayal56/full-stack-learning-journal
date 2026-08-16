# Introduction to Angular

Today I studied the basics of Angular, its benefits, and the setup process. Here are my notes:

## 1. What is Angular and why use it?

- Angular is a very popular JavaScript framework created and maintained by **Google**. It is used to build web apps.
- **Performance:** It loads fast and updates the screen quickly. Managing code is easy (modularity), it has "dependency injection" to share services, and testing is also easy.
- **Mobile Support:** With Angular, we can build a single application that runs well on both mobile and desktop without any third-party tools.
- **Language:** We write Angular apps in TypeScript (which is the most popular choice).

## 2. ECMAScript vs TypeScript

- **ECMAScript:** This is the official standard name for JavaScript. Every year a new version is released with new features (like ES6/ES2015 which introduced classes, modules, etc.).
- **TypeScript:** It was created by Microsoft. It is a "superset" of JavaScript, meaning it includes all of JavaScript, but has some extra features on top (like **Types**, Interfaces, Classes). To run it, it is first compiled and converted back into plain JavaScript. This makes writing and maintaining code much easier.

## 3. Angular Setup & Installation

1. **Install Node.js:** Angular runs on Node.js. (To check: `node -v` and `npm -v`)
2. **Install Angular CLI:** Write in terminal: `npm install -g @angular/cli`. (To check: `ng version`)
3. **Create and Run First App:**
   - To create a new project: `ng new my-first-app`
   - To go to the folder: `cd my-first-app`
   - To run the app: `ng serve`
   - Open in browser: `http://localhost:4200`

## 4. What is Angular CLI (Command Line Interface)?

CLI is a helper tool that runs in the terminal. It automates boring and manual tasks for us like setting up the project, creating new files, and running the app, so that our focus remains only on writing the app's code.

**Most Used CLI Commands:**

- `ng new <name>` : Creates a new project.
- `ng serve` : Runs the app on the local machine and auto-reloads as soon as the code is saved.
- `ng generate component <name>` (short: `ng g c <name>`) : Creates a new component along with all its files.
- `ng build` : Packages the app for final deployment.
- `ng test` : Runs tests.