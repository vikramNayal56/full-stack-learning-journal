# Angular Forms & Routing

Today I learned about the two types of forms in Angular and how to set up Routing with Lazy Loading. Here are my notes:

## 1. Angular Forms

Angular provides two distinct approaches to handling user input through forms.

### A. Template-Driven Forms
- **Best For:** Simple forms (like a basic login or contact form).
- **Module Required:** `FormsModule`
- **How it works:** The logic and validations are mostly written in the HTML template. It uses two-way data binding with the `[(ngModel)]` directive.
- **Testing:** Harder to test because the logic is tightly coupled with the HTML UI.

### B. Reactive Forms (Model-Driven)
- **Best For:** Complex forms (like multi-step wizards, dynamic fields, or heavy validations).
- **Module Required:** `ReactiveFormsModule`
- **How it works:** The form structure, logic, and validations are defined in the TypeScript component class using `FormGroup`, `FormControl`, and `FormBuilder`. The HTML simply binds to these existing objects.
- **Testing:** Very easy to unit test because all the logic lives in the TS class.

*Rule of thumb:* Reactive forms are considered the standard and most professional approach for enterprise-level Angular applications due to their scalability and testability.

## 2. Angular Routing & Lazy Loading

Routing is how an Angular single-page application (SPA) navigates between different views (components) without reloading the page.

### A. Basic Routing
We define routes in an array where each object maps a specific `path` (URL) to a specific `component`.
Example: `{ path: 'login', component: LoginComponent }`

### B. Lazy Loading
If an application is large, downloading all the code at once (Eager Loading) makes the initial load very slow. Lazy Loading solves this.
- **How it works:** Instead of loading all components upfront, Angular only downloads the code for a specific feature module when the user actually navigates to its route.
- **Syntax:** We use the `loadChildren` property in the main routing file.
  Example: `{ path: 'practice', loadChildren: () => import('./forms-practice/forms-practice.module').then(m => m.FormsPracticeModule) }`
- **Benefit:** Significantly improves the initial load time and performance of the application.