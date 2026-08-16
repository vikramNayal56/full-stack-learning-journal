# HTML (HyperText Markup Language)

HTML is the standard markup language used to create the **structure of a webpage**. It defines what each element represents, while CSS is responsible for its appearance.

---

## Basic HTML Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Website</title>
</head>

<body>

</body>
</html>
```

### Common HTML Tags

| Tag               | Purpose                     |
| ----------------- | --------------------------- |
| `<!DOCTYPE html>` | Declares an HTML5 document  |
| `<html>`          | Root element of the webpage |
| `<head>`          | Stores metadata             |
| `<title>`         | Browser tab title           |
| `<body>`          | Visible webpage content     |

---

## Common HTML Elements

| Tag                    | Purpose              |
| ---------------------- | -------------------- |
| `<h1>` - `<h6>`        | Headings             |
| `<p>`                  | Paragraph            |
| `<a>`                  | Hyperlink            |
| `<img>`                | Image                |
| `<ul>`, `<ol>`, `<li>` | Lists                |
| `<table>`              | Display tabular data |
| `<form>`               | Collect user input   |

---

# Semantic HTML

Semantic elements describe the **purpose of the content** instead of using generic `<div>` elements everywhere.

## Common Semantic Elements

| Tag         | Purpose                    |
| ----------- | -------------------------- |
| `<header>`  | Top section of the webpage |
| `<nav>`     | Navigation links           |
| `<main>`    | Main content               |
| `<section>` | Related content            |
| `<article>` | Independent content        |
| `<aside>`   | Sidebar or extra content   |
| `<footer>`  | Bottom section             |

### Why Semantic HTML?

* Improves code readability.
* Makes webpages more accessible.
* Helps search engines understand page structure.
* Makes code easier to maintain.

---

## `<div>` vs `<span>`

| `<div>`                      | `<span>`                         |
| ---------------------------- | -------------------------------- |
| Block-level element          | Inline element                   |
| Used for larger sections     | Used for small pieces of content |
| Usually starts on a new line | Stays within the same line       |

---

# HTML Forms

Forms are used to **collect information from users**.

## Common Input Types

| Type       | Purpose             |
| ---------- | ------------------- |
| `text`     | Text input          |
| `email`    | Email address       |
| `password` | Password            |
| `number`   | Numeric input       |
| `date`     | Date selection      |
| `checkbox` | Multiple selections |
| `radio`    | Single selection    |

### Example

```html
<form>
    <input type="text" placeholder="Enter your name">
    <input type="email" placeholder="Enter your email">
    <input type="password" placeholder="Enter password">

    <input type="checkbox"> Subscribe

    <button type="submit">Submit</button>
</form>
```

---

# Quick Revision

* **HTML** → Webpage structure
* **Semantic HTML** → Meaningful elements
* **`<div>`** → Block-level container
* **`<span>`** → Inline container
* **`alt`** → Image description/accessibility
* **Forms** → Collect user input
* **Tables** → Display tabular data
* **CSS** → Styling and appearance
* **JavaScript** → Behaviour and interactivity