# Angular Components & Communication

Today, I learned about Angular Components and got a basic introduction to how they communicate. Here is a summary of what I covered:

## 1. What is a Component?

A component is essentially a reusable and independent piece of the User Interface (UI). It contains its own HTML (structure), CSS (styles), and logic (TypeScript).

## 2. Why do we use Components?

- **Reusability:** We can write code once and use it in multiple places.
- **Easy Maintenance:** Since the UI is broken down into smaller pieces, finding and fixing bugs becomes easier.
- **Consistency:** Ensures our app has a uniform look and feel.
- **Testing & Teamwork:** Smaller independent pieces are easier to test, and multiple developers can work on different components at the same time.

## 3. Structure of an Angular Component

An Angular component is made up of three main parts in the code:

1. **A Class:** Where we write our logic (TypeScript).
2. **A Template:** The HTML view of the component.
3. **A Decorator:** Specifically, the `@Component` decorator which tells Angular that the class is a component. It includes metadata like the `selector` (how we use it in HTML) and the `templateUrl`/`styleUrls`.

## 4. Working with Components

- **Creating a component:** We use the Angular CLI command `ng generate component <component-name>` to quickly set up a new component.
- **Data Binding:** We can display data from our class in the HTML template using interpolation, which looks like `{{ propertyName }}`.
- **Displaying a component:** We use the component's `selector` as an HTML tag (e.g., `<app-header></app-header>`) to place it anywhere on the page.

## 5. Component Communication (Theory)

I also learned the basic concept of how components talk to each other:

- Components often have a **Parent-Child** relationship.
- **`@Input`:** Used by a child component to receive data passed down from its parent.
- **`@Output`:** Used by a child component to send events or data back up to its parent.
  _(I will be doing hands-on practice for this tomorrow!)_