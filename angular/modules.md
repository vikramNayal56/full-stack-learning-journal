# Angular Modules & Component Communication (Theory)

Today, I learned about Angular Modules (NgModule) and dived deeper into the theory of Component Communication. Here are my notes:

## 1. What is an Angular Module (NgModule)?

An Angular Module (`NgModule`) is like a container or a box that groups related parts of our application together. It holds:

- **Declarations:** The components, directives, and pipes that belong to this module.
- **Imports:** Other modules whose exported classes are needed by component templates in this module.
- **Exports:** The subset of declarations that should be visible and usable in the component templates of other modules.
- **Providers:** Services that this module contributes to the global collection of services.

## 2. Why do we need Modules?

Modules exist for a few key reasons:

- **Organisation:** They help in keeping related code together (like a `UserModule` or `ProductModule`).
- **Reusability:** A module can be easily exported and reused in other parts of the application or even in different projects.
- **Separation of Concerns:** Helps in maintaining a clean architecture by dividing the app into distinct feature areas.
- **Lazy Loading:** We can load modules only when they are needed (e.g., when a user navigates to a specific route), which makes the initial loading of the app much faster.

## 3. The Shift to Standalone Components

_Important Note:_ While learning modules is essential for reading and maintaining older codebases, modern Angular uses **Standalone Components** by default. This means modules are now completely optional, and we will mostly be using standalone components for any new work.

## 4. Component Communication: @Input and @Output

I also learned how data flows between parent and child components:

- **`@Input()`:** This is used when a parent component wants to send data _down_ to a child component. We use square brackets `[ ]` in the HTML to pass this data (e.g., `[data]="parentData"`).
- **`@Output()`:** This is used when a child component wants to send an event or data _up_ to its parent. It uses an `EventEmitter` and `$event`. We use round brackets `( )` in the HTML to listen for these events (e.g., `(customEvent)="handleEvent($event)"`).
  _(I'll be doing hands-on practice for this tomorrow!)_

---

**1. What is a module, and two reasons modules exist**
A module in Angular is essentially a container that groups related components, services, and other files together. Think of it like a folder that organizes a specific feature of the app.
Two main reasons modules exist are:

- **Organisation:** It keeps related code grouped together, making the project easier to navigate and maintain.
- **Lazy Loading:** It allows us to load only the parts of the app that the user is currently accessing, speeding up the app's initial load time.

**2. Why did Angular move from modules to standalone components?**
Angular moved to standalone components to simplify the learning curve and reduce boilerplate code. With NgModules, developers had to jump between the component file and the module file to declare and configure things, which was confusing and tedious. Standalone components make things more straightforward by allowing a component to manage its own dependencies directly, making the code much easier to write, read, and maintain.