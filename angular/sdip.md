# Services, Dependency Injection & Pipes

Today I learned about Angular Services, Singletons, and Pipes. Here are my key takeaways in my own words:

## 1. What is an Angular Service?
A service is just a plain TypeScript class used to store logic and data that I want to share across multiple components in my app. 
Instead of writing the same code (like fetching API data, storing logged-in users, etc.) in every component, I can put it in a service to keep my components clean and light.
- **Rule of thumb:** Components are just for the view (UI), and services handle the shared data/logic behind the scenes.
- To make a class a service, we use the `@Injectable` decorator. The command `ng generate service <name>` (or `ng g s <name>`) creates this for us automatically.

## 2. Dependency Injection (DI)
When a component needs a service, it doesn't create the service itself (no `new` keyword). Instead, it just "asks" Angular for it inside the constructor, and Angular hands it over. This process is called Dependency Injection.
- **Analogy:** It's like plugging a charger into the wall. I don't build my own electricity generator; I just plug into the socket, and electricity is provided to me.

## 3. The Singleton Concept
When a service is marked with `providedIn: 'root'`, Angular creates only **one single shared instance** of it for the entire app. This is known as a Singleton.
- Because there is only one shared copy, if one component updates the data in the service, all other components that use that service will immediately see the updated data.
- **Real-life Examples:**
  1. A single TV remote shared by a family.
  2. One washing machine shared by the whole house.
  3. A single shopping cart you carry around different stores in a mall.

## 4. Pipes
Pipes are a neat feature in Angular used to format data directly in the HTML template without changing the actual underlying data in the TypeScript file. We use the `|` symbol for it.
- **Built-in Pipes:** Angular comes with useful pipes like `uppercase`, `lowercase`, `date`, `currency`, `percent`, etc.
  Example: `{{ name | uppercase }}`
- **Custom Pipes:** If I need a specific format that Angular doesn't provide, I can create my own pipe using the `@Pipe` decorator and the `transform` method. The command to create one is `ng generate pipe <name>`.
  Example: I created a `double` pipe that takes a number and multiplies it by 2: `{{ 10 | double }}` -> 20.