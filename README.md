# MEAN Stack Full Stack Web Developer — Complete Study Notes

*Comprehensive theory + examples, aligned to the 8-unit syllabus*

---

## Table of Contents
1. Unit 1: Induction to Full Stack Web Development (MEAN Stack)
2. Unit 2: Fundamentals of Web Development
3. Unit 3: Frontend Development with Angular
4. Unit 4: Introduction to Node.js
5. Unit 6: Introduction to Express.js
6. Unit 7: Introduction to NoSQL & MongoDB
7. Unit 8: Integrating & Deploying a MEAN App
8. Quick-Revision Cheat Sheets
9. Suggested Practice Projects

---

## UNIT 1: Induction for Full Stack Web Developer — MEAN Stack
*(4 Lectures)*

### 1.1 What is a Full Stack Web Developer?

A **Full Stack Web Developer** is someone who can work on all layers of a web application:

- **Frontend (Client-side):** What the user sees and interacts with — layout, styling, interactivity (HTML, CSS, JavaScript, and a framework like Angular/React/Vue).
- **Backend (Server-side):** Business logic, authentication, APIs, and communication with the database (Node.js, Express.js, Django, Spring, etc.).
- **Database:** Persistent storage of data (MongoDB, MySQL, PostgreSQL).
- **DevOps/Deployment basics:** Version control (Git), hosting, CI/CD, servers.

**Why full stack matters:**
- Faster prototyping — one person/team can build an entire product.
- Better understanding of how data flows end-to-end (helps debugging).
- High demand in startups and small teams where hiring specialists for every layer isn't feasible.

### 1.2 Approaches to Web Development

| Approach | Description | Example |
|---|---|---|
| **Static Website** | Fixed content, same for every user, no server-side processing | Plain HTML/CSS portfolio site |
| **Dynamic Website** | Content generated on the fly based on user/data | E-commerce site showing personalized recommendations |
| **Client-Side Rendering (CSR)** | Browser downloads JS bundle, renders UI in browser | Angular/React SPA |
| **Server-Side Rendering (SSR)** | HTML generated on server per request | Next.js, traditional PHP/JSP apps |
| **Single Page Application (SPA)** | One HTML shell, JS swaps views without full reloads | Gmail, Angular apps |
| **Multi Page Application (MPA)** | Every navigation reloads a new HTML page from server | Traditional e-commerce sites |
| **JAMstack** | JavaScript + APIs + prebuilt Markup, served via CDN | Gatsby/Next static sites |

### 1.3 Introduction to Different Technologies

**Frontend technologies:** HTML, CSS, JavaScript, TypeScript, Angular, React, Vue, Bootstrap, Tailwind CSS.

**Backend technologies:** Node.js, Express.js, Django (Python), Spring Boot (Java), Ruby on Rails, .NET.

**Databases:**
- **Relational (SQL):** MySQL, PostgreSQL, Oracle — structured tables, fixed schema, ACID transactions.
- **Non-Relational (NoSQL):** MongoDB, Cassandra, Redis — flexible schema, horizontal scaling, good for unstructured/semi-structured data.

**MEAN Stack — the four pillars:**
| Letter | Technology | Role |
|---|---|---|
| **M** | MongoDB | NoSQL database for storing data as JSON-like documents |
| **E** | Express.js | Backend web framework (runs on Node.js) for building REST APIs |
| **A** | Angular | Frontend framework for building SPAs |
| **N** | Node.js | JavaScript runtime that executes server-side code |

**Why MEAN?**
- Single language (JavaScript/TypeScript) across the entire stack → less context switching.
- JSON flows naturally from MongoDB → Express → Angular (all JS-based), reducing data-transformation overhead.
- Strong ecosystem via npm (Node Package Manager).
- Great for building scalable, real-time, data-driven SPAs.

**Example — data flow in a MEAN app:**
```
Browser (Angular) 
   --HTTP request (GET /api/students)-->
Express.js route 
   --queries-->
MongoDB (returns JSON documents)
   --Express sends JSON response-->
Angular (renders data using components/services)
```

**Other common stacks for comparison:**
- **MERN** = MongoDB + Express + React + Node (React instead of Angular)
- **LAMP** = Linux + Apache + MySQL + PHP
- **MEVN** = MongoDB + Express + Vue + Node

---

## UNIT 2: Fundamentals of Web Development
*(5 Lectures)*

### 2.1 Agile and Scrum Methodologies

**Agile** is a project management philosophy focused on iterative development, collaboration, and responding to change over following a rigid plan.

**Agile Manifesto values:**
1. Individuals and interactions over processes and tools
2. Working software over comprehensive documentation
3. Customer collaboration over contract negotiation
4. Responding to change over following a plan

**Scrum** is the most widely used Agile framework. Key elements:

| Element | Description |
|---|---|
| **Sprint** | Fixed time-box (usually 1–4 weeks) to deliver a working increment |
| **Product Backlog** | Prioritized list of all features/requirements |
| **Sprint Backlog** | Subset of backlog items chosen for the current sprint |
| **Scrum Master** | Facilitates the process, removes blockers |
| **Product Owner** | Represents stakeholders, prioritizes backlog |
| **Development Team** | Builds the product increment |
| **Daily Stand-up** | 15-min daily sync — what I did, what I'll do, blockers |
| **Sprint Review** | Demo completed work to stakeholders |
| **Sprint Retrospective** | Team reflects on what went well/what to improve |

**Example:** A team building "PulseTalk" (a chat app) might break work into sprints: Sprint 1 — auth & user profiles; Sprint 2 — real-time messaging; Sprint 3 — video calls, etc.

### 2.2 HTML, CSS, and JavaScript

#### HTML (HyperText Markup Language) — structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>My First Page</title>
</head>
<body>
  <h1>Hello World</h1>
  <p>This is a paragraph.</p>
  <a href="https://example.com">Visit Example</a>
</body>
</html>
```

Key concepts: semantic tags (`<header>`, `<nav>`, `<main>`, `<footer>`, `<section>`, `<article>`), forms (`<form>`, `<input>`, `<button>`), tables, and the DOM (Document Object Model) — the tree-like in-memory representation of the HTML page that JavaScript can manipulate.

#### CSS (Cascading Style Sheets) — presentation

```css
body {
  font-family: Arial, sans-serif;
  background-color: #f4f4f4;
}

.card {
  display: flex;
  justify-content: space-between;
  padding: 16px;
  border-radius: 8px;
  box-shadow: 0 2px 6px rgba(0,0,0,0.1);
}
```

Key concepts:
- **Box Model:** content → padding → border → margin.
- **Selectors:** element, class (`.name`), id (`#name`), pseudo-classes (`:hover`), attribute selectors.
- **Layout systems:** Flexbox (1-D layouts) and CSS Grid (2-D layouts).
- **Responsive design:** media queries (`@media (max-width: 768px) {...}`), relative units (`rem`, `%`, `vh/vw`).
- **Specificity & cascade:** inline styles > IDs > classes > elements, and later rules override earlier ones of equal specificity.

#### JavaScript (JS) — behavior

```javascript
// Variables & functions
const greetUser = (name) => `Hello, ${name}!`;
console.log(greetUser("Bug Master"));

// DOM manipulation
document.querySelector("#btn").addEventListener("click", () => {
  document.querySelector("#output").textContent = "Button clicked!";
});

// Fetch API (asynchronous)
async function getUsers() {
  const res = await fetch("https://api.example.com/users");
  const data = await res.json();
  console.log(data);
}
```

Key concepts:
- **Data types & variables:** `let`, `const` (avoid `var`), primitive vs reference types.
- **Functions:** regular, arrow functions, higher-order functions (`map`, `filter`, `reduce`).
- **Asynchronous JS:** callbacks → Promises → `async/await`.
- **DOM events:** `addEventListener`, event bubbling/capturing.
- **ES6+ features:** template literals, destructuring, spread/rest operators, modules (`import`/`export`).

### 2.3 Git — Version Control

**Git** is a distributed version control system that tracks changes to code over time and enables collaboration.

**Core concepts:**
- **Repository (repo):** A project tracked by Git.
- **Commit:** A snapshot of changes with a message.
- **Branch:** An independent line of development (e.g., `main`, `feature/login`).
- **Merge/Rebase:** Combining changes from different branches.
- **Remote:** A hosted version of the repo (e.g., on GitHub).

**Common commands:**
```bash
git init                        # initialize a new repo
git clone <url>                 # copy a remote repo locally
git status                      # see changed files
git add .                       # stage all changes
git commit -m "message"         # commit staged changes
git push origin main            # push commits to remote
git pull origin main            # fetch + merge remote changes
git branch feature/chat-ui      # create a new branch
git checkout feature/chat-ui    # switch to that branch
git merge feature/chat-ui       # merge into current branch
git log --oneline               # view commit history
```

**Typical workflow (feature branching):**
1. `git checkout -b feature/x` — create a feature branch
2. Make changes, commit regularly
3. Push branch, open a Pull Request (PR)
4. Code review → merge into `main`

---

## UNIT 3: Frontend Development with Angular
*(12 Lectures)*

### 3.1 Frontend vs Backend Web Development

| Aspect | Frontend | Backend |
|---|---|---|
| Runs on | Browser (client) | Server |
| Concerned with | UI/UX, presentation, interactivity | Business logic, data, security |
| Technologies | HTML, CSS, JS, Angular/React | Node.js, Express, databases |
| Communicates via | HTTP requests (Ajax/Fetch) | REST APIs, GraphQL |

### 3.2 Introduction to Angular

**Angular** is a TypeScript-based, component-driven front-end framework maintained by Google, used to build Single Page Applications (SPAs).

**Key features:**
- Component-based architecture
- Two-way data binding
- Dependency Injection (DI)
- Built-in Router for SPA navigation
- RxJS for reactive/async programming
- CLI tooling (`ng` commands) for scaffolding, building, testing

**Angular CLI basics:**
```bash
npm install -g @angular/cli
ng new my-app
cd my-app
ng serve            # dev server at localhost:4200
ng generate component navbar     # or: ng g c navbar
ng generate service auth          # or: ng g s auth
ng build --configuration production
```

### 3.3 TypeScript and ES6

**TypeScript** is a superset of JavaScript that adds static typing, compiled down to plain JS.

```typescript
// Basic types
let username: string = "BugMaster";
let age: number = 25;
let isActive: boolean = true;
let hobbies: string[] = ["coding", "reading"];

// Interfaces
interface User {
  id: number;
  name: string;
  email?: string;   // optional property
}

const user: User = { id: 1, name: "Bug Master" };

// Classes
class Person {
  constructor(private name: string, public age: number) {}
  greet(): string {
    return `Hi, I'm ${this.name}`;
  }
}

// Generics
function identity<T>(value: T): T {
  return value;
}
```

**Why TypeScript in Angular:** catches errors at compile-time, better IDE autocomplete, easier refactoring in large codebases, and Angular itself is written in TypeScript.

**Key ES6+ features used heavily in Angular:**
```javascript
// Destructuring
const { name, age } = user;

// Spread/rest
const newArr = [...oldArr, newItem];

// Arrow functions
const square = (x) => x * x;

// Modules
import { Component } from '@angular/core';
export class AppComponent {}

// Template literals
const message = `Welcome, ${name}!`;
```

### 3.4 Components in Angular

A **Component** controls a patch of screen (a "view") and consists of three parts:
1. **TypeScript class** — logic and data
2. **HTML template** — view
3. **CSS file** — styling

```typescript
// user-card.component.ts
import { Component, Input } from '@angular/core';

@Component({
  selector: 'app-user-card',
  templateUrl: './user-card.component.html',
  styleUrls: ['./user-card.component.css']
})
export class UserCardComponent {
  @Input() username: string = '';
  isOnline: boolean = true;

  toggleStatus() {
    this.isOnline = !this.isOnline;
  }
}
```

```html
<!-- user-card.component.html -->
<div class="card">
  <h3>{{ username }}</h3>
  <button (click)="toggleStatus()">
    {{ isOnline ? 'Online' : 'Offline' }}
  </button>
</div>
```

Used elsewhere as: `<app-user-card [username]="'Bug Master'"></app-user-card>`

### 3.5 Data Binding and Event Binding

| Type | Syntax | Direction | Example |
|---|---|---|---|
| Interpolation | `{{ value }}` | Component → View | `<p>{{ title }}</p>` |
| Property Binding | `[property]="value"` | Component → View | `<img [src]="imageUrl">` |
| Event Binding | `(event)="handler()"` | View → Component | `<button (click)="save()">` |
| Two-way Binding | `[(ngModel)]="value"` | Both | `<input [(ngModel)]="name">` |

```html
<!-- Two-way binding example (requires FormsModule) -->
<input [(ngModel)]="searchTerm" placeholder="Search...">
<p>You typed: {{ searchTerm }}</p>
```

### 3.6 Structural Directives, Attribute Directives, Property Bindings

**Structural directives** change the DOM layout by adding/removing elements. Prefixed with `*`.

```html
<!-- *ngIf -->
<p *ngIf="isLoggedIn">Welcome back!</p>

<!-- *ngFor -->
<ul>
  <li *ngFor="let item of items; let i = index">
    {{ i + 1 }}. {{ item.name }}
  </li>
</ul>

<!-- *ngSwitch -->
<div [ngSwitch]="userRole">
  <p *ngSwitchCase="'admin'">Admin Panel</p>
  <p *ngSwitchCase="'user'">User Dashboard</p>
  <p *ngSwitchDefault>Guest View</p>
</div>
```

**Attribute directives** change the appearance/behavior of an element without changing DOM structure.

```html
<p [ngClass]="{ 'highlight': isActive, 'faded': !isActive }">Status text</p>
<div [ngStyle]="{ 'color': isError ? 'red' : 'green' }">Message</div>
```

**Custom directive example:**
```typescript
@Directive({ selector: '[appHighlight]' })
export class HighlightDirective {
  constructor(private el: ElementRef) {
    el.nativeElement.style.backgroundColor = 'yellow';
  }
}
```

### 3.7 Template-Driven vs Model-Driven (Reactive) Forms

**Template-Driven Forms** — logic mostly in HTML, uses `ngModel`. Good for simple forms.

```html
<form #loginForm="ngForm" (ngSubmit)="onSubmit(loginForm.value)">
  <input name="email" ngModel required email>
  <input name="password" ngModel required minlength="6" type="password">
  <button type="submit" [disabled]="loginForm.invalid">Login</button>
</form>
```

**Reactive (Model-Driven) Forms** — logic in the TypeScript class using `FormGroup`/`FormControl`. Better for complex, dynamic, testable forms.

```typescript
import { FormGroup, FormControl, Validators } from '@angular/forms';

export class SignupComponent {
  signupForm = new FormGroup({
    email: new FormControl('', [Validators.required, Validators.email]),
    password: new FormControl('', [Validators.required, Validators.minLength(6)])
  });

  onSubmit() {
    if (this.signupForm.valid) {
      console.log(this.signupForm.value);
    }
  }
}
```
```html
<form [formGroup]="signupForm" (ngSubmit)="onSubmit()">
  <input formControlName="email">
  <input formControlName="password" type="password">
  <button type="submit" [disabled]="signupForm.invalid">Sign Up</button>
</form>
```

### 3.8 Pipes and Data Formatting

**Pipes** transform displayed data without changing the underlying value.

```html
<p>{{ price | currency:'INR' }}</p>          <!-- ₹1,234.00 -->
<p>{{ today | date:'longDate' }}</p>         <!-- August 1, 2026 -->
<p>{{ name | uppercase }}</p>
<p>{{ description | slice:0:50 }}...</p>
<p>{{ user | json }}</p>
```

**Custom pipe:**
```typescript
@Pipe({ name: 'truncate' })
export class TruncatePipe implements PipeTransform {
  transform(value: string, limit: number = 20): string {
    return value.length > limit ? value.substring(0, limit) + '...' : value;
  }
}
```
Usage: `{{ longText | truncate:30 }}`

### 3.9 Services and Dependency Injection

A **Service** is a reusable class that holds logic/data separate from components (e.g., API calls). **Dependency Injection (DI)** is how Angular provides an instance of a service to a component automatically.

```typescript
@Injectable({ providedIn: 'root' })   // singleton, tree-shakable
export class UserService {
  constructor(private http: HttpClient) {}

  getUsers(): Observable<User[]> {
    return this.http.get<User[]>('/api/users');
  }
}
```

```typescript
@Component({ selector: 'app-user-list', templateUrl: './user-list.component.html' })
export class UserListComponent implements OnInit {
  users: User[] = [];

  constructor(private userService: UserService) {}   // DI happens here

  ngOnInit() {
    this.userService.getUsers().subscribe(data => this.users = data);
  }
}
```

**Why DI matters:** promotes loose coupling, easier unit testing (services can be mocked), and single-responsibility design.

### 3.10 Single Page Applications (SPA)

An SPA loads a single HTML page and dynamically updates content as the user interacts, without full page reloads — giving an app-like feel.

**Advantages:** faster navigation after initial load, smoother UX, clear separation of frontend/backend via APIs.
**Disadvantages:** larger initial bundle size, SEO can be harder (mitigated with SSR/Angular Universal), requires JS enabled.

### 3.11 Angular Router (Component Router)

The Router enables navigation between views/components without reloading the page.

```typescript
const routes: Routes = [
  { path: '', component: HomeComponent },
  { path: 'chats/:id', component: ChatDetailComponent },
  { path: 'profile', component: ProfileComponent, canActivate: [AuthGuard] },
  { path: '**', component: PageNotFoundComponent }   // wildcard/404
];

@NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule {}
```

```html
<nav>
  <a routerLink="/">Home</a>
  <a routerLink="/profile" routerLinkActive="active">Profile</a>
</nav>
<router-outlet></router-outlet>   <!-- matched component renders here -->
```

**Route guards:** `CanActivate` (protect a route), `CanDeactivate` (confirm before leaving, e.g. unsaved form), `Resolve` (pre-fetch data before route loads).

### 3.12 Modules

An Angular app is organized into **NgModules** — containers that group related components, directives, pipes, and services.

```typescript
@NgModule({
  declarations: [AppComponent, ChatListComponent, ChatDetailComponent],
  imports: [BrowserModule, FormsModule, ReactiveFormsModule, HttpClientModule, AppRoutingModule],
  providers: [UserService],
  bootstrap: [AppComponent]
})
export class AppModule {}
```

- **Root module (`AppModule`):** bootstraps the app.
- **Feature modules:** organize related functionality (e.g., `ChatModule`, `AuthModule`).
- **Lazy-loaded modules:** loaded only when their route is visited, improving initial load time:
```typescript
{ path: 'chat', loadChildren: () => import('./chat/chat.module').then(m => m.ChatModule) }
```

### 3.13 Deploying an Angular App

```bash
ng build --configuration production
```
This generates optimized static files (HTML/CSS/JS bundles) in the `dist/` folder — AOT-compiled, minified, and tree-shaken.

**Deployment targets:**
- **Static hosting:** Netlify, Vercel, GitHub Pages, Firebase Hosting.
- **Node/Express server:** serve the `dist/` folder as static files via `express.static()`.
- **Cloud platforms:** AWS S3 + CloudFront, Azure Static Web Apps.

**Common gotcha:** SPA routing requires the server to redirect all unknown routes back to `index.html` (so Angular's router can take over client-side), e.g. a `_redirects` file on Netlify or a catch-all route in Express.

---

## UNIT 4: Introduction to Node.js
*(6 Lectures)*

### 4.1 What is Node.js?

**Node.js** is a runtime environment that executes JavaScript outside the browser, built on Chrome's **V8 JavaScript engine**. It enables JavaScript to be used for server-side programming.

### 4.2 Why Node.js? Key Features

| Feature | Explanation |
|---|---|
| **Single-threaded, event-driven** | Uses a single main thread with an event loop instead of spawning a thread per request |
| **Non-blocking I/O** | I/O operations (file, network, DB) don't block execution; callbacks/promises handle results when ready |
| **Fast execution** | V8 compiles JS to native machine code |
| **NPM ecosystem** | Largest package registry in the world (npm) |
| **Cross-platform** | Runs on Windows, macOS, Linux |
| **Same language as frontend** | JavaScript everywhere reduces context-switching (key MEAN advantage) |

### 4.3 Installation & Configuration

```bash
# Verify installation
node -v
npm -v

# Initialize a project
npm init -y          # creates package.json

# Install dependencies
npm install express
npm install --save-dev nodemon   # dev-only dependency

# Run a file
node server.js
```

`package.json` tracks project metadata and dependencies:
```json
{
  "name": "my-backend",
  "version": "1.0.0",
  "scripts": {
    "start": "node server.js",
    "dev": "nodemon server.js"
  },
  "dependencies": { "express": "^4.18.0" }
}
```

### 4.4 Where to Use Node.js

- REST APIs and backend services
- Real-time applications (chat apps, live notifications) via WebSockets/Socket.io
- Microservices
- Command-line tools
- Streaming applications
- NOT ideal for: heavy CPU-bound tasks (e.g., video encoding, complex ML computation) since it's single-threaded — better handled by worker threads or a different language/service.

### 4.5 Server-Side JavaScript — Basic Example

```javascript
// Using core 'http' module (no framework)
const http = require('http');

const server = http.createServer((req, res) => {
  res.writeHead(200, { 'Content-Type': 'text/plain' });
  res.end('Hello from Node.js server!');
});

server.listen(3000, () => console.log('Server running on port 3000'));
```

### 4.6 Asynchronous Events vs. Threads

**Traditional multi-threaded servers (e.g., Apache/Java):** each incoming request gets its own thread. Threads are expensive (memory, context switching) — doesn't scale well with thousands of concurrent connections.

**Node.js model:** single main thread + **event loop**. Blocking operations (file reads, DB queries, network calls) are delegated to the system/**libuv thread pool**, and a callback fires on the event loop once the operation completes.

```javascript
console.log('1: Start');

setTimeout(() => console.log('2: Timeout callback'), 0);

fs.readFile('data.txt', 'utf8', (err, data) => {
  console.log('3: File read callback');
});

console.log('4: End');

// Output order: 1: Start -> 4: End -> 3/2 (async callbacks after sync code finishes)
```

**Event loop phases (simplified):** timers → pending callbacks → poll (I/O) → check (`setImmediate`) → close callbacks.

### 4.7 Performance and Server Utilization

- Node.js handles **high concurrency with low memory overhead** because it doesn't spawn a thread per connection — ideal for I/O-heavy apps (APIs, chat, streaming) with many simultaneous but lightweight connections.
- **CPU-bound work is the weak point** — a long synchronous computation blocks the single event loop for *all* users. Mitigations: `worker_threads` module, offloading to separate microservices, or clustering (`cluster` module to use multiple CPU cores).
- **Clustering example:**
```javascript
const cluster = require('cluster');
const os = require('os');

if (cluster.isPrimary) {
  os.cpus().forEach(() => cluster.fork());
} else {
  require('./server');   // each worker runs the actual server
}
```

---

## UNIT 6: Introduction to Express.js
*(12 Lectures)*

### 6.1 What is Express.js?

**Express.js** is a minimal, unopinionated web framework for Node.js that simplifies building web servers and REST APIs — handling routing, middleware, request/response objects.

```javascript
const express = require('express');
const app = express();
app.use(express.json());   // parse JSON request bodies

app.get('/', (req, res) => res.send('Hello Express!'));

app.listen(3000, () => console.log('Server on port 3000'));
```

### 6.2 Routing in Express.js

Routing determines how the app responds to a client request to a particular endpoint (URL + HTTP method).

```javascript
app.get('/api/users', (req, res) => { res.json([{ id: 1, name: 'Alice' }]); });
app.post('/api/users', (req, res) => { /* create user */ res.status(201).json(req.body); });
app.put('/api/users/:id', (req, res) => { /* update user by id */ res.json({ id: req.params.id, ...req.body }); });
app.delete('/api/users/:id', (req, res) => { res.status(204).send(); });

// Route parameters and query strings
app.get('/api/users/:id', (req, res) => {
  const { id } = req.params;              // /api/users/5  -> id = '5'
  const { fields } = req.query;           // /api/users/5?fields=name
  res.json({ id, fields });
});

// Using Router for modular routes
const router = express.Router();
router.get('/', (req, res) => res.send('All chats'));
router.get('/:id', (req, res) => res.send(`Chat ${req.params.id}`));
app.use('/api/chats', router);
```

### 6.3 Middleware in Express.js

**Middleware** are functions that execute during the request-response cycle, with access to `req`, `res`, and `next()`. Used for logging, auth, parsing, error-handling, etc.

```javascript
// Custom middleware
function logger(req, res, next) {
  console.log(`${req.method} ${req.url} - ${new Date().toISOString()}`);
  next();   // pass control to the next middleware/route handler
}
app.use(logger);

// Built-in / third-party middleware
app.use(express.json());               // parse JSON bodies
app.use(express.urlencoded({ extended: true }));   // parse form data
app.use(require('cors')());             // enable CORS
app.use(require('morgan')('dev'));      // HTTP request logging

// Route-specific middleware
function authenticate(req, res, next) {
  if (!req.headers.authorization) return res.status(401).json({ error: 'Unauthorized' });
  next();
}
app.get('/api/profile', authenticate, (req, res) => res.json({ user: 'Bug Master' }));
```

Middleware types: **application-level**, **router-level**, **error-handling**, **built-in**, **third-party**.

### 6.4 Templating Engines with Express.js

Templating engines render dynamic HTML on the server (SSR). Common ones: **EJS**, **Pug**, **Handlebars**.

```javascript
app.set('view engine', 'ejs');
app.set('views', './views');

app.get('/profile', (req, res) => {
  res.render('profile', { name: 'Bug Master', role: 'Developer' });
});
```
```html
<!-- views/profile.ejs -->
<h1>Welcome, <%= name %></h1>
<p>Role: <%= role %></p>
```
*(Note: in a MEAN app, Angular usually handles the view layer, so Express mainly serves JSON APIs — templating engines are more relevant to traditional MVC apps.)*

### 6.5 Handling Static Files

```javascript
app.use(express.static('public'));   // serves files from ./public directly
// e.g. public/logo.png is now accessible at http://localhost:3000/logo.png
```

### 6.6 Error Handling

```javascript
// Async route error handling
app.get('/api/data', async (req, res, next) => {
  try {
    const data = await fetchData();
    res.json(data);
  } catch (err) {
    next(err);   // forward to error-handling middleware
  }
});

// Centralized error-handling middleware (must have 4 params, placed LAST)
app.use((err, req, res, next) => {
  console.error(err.stack);
  res.status(err.status || 500).json({ error: err.message || 'Internal Server Error' });
});

// 404 handler (placed before the error handler, after all routes)
app.use((req, res) => res.status(404).json({ error: 'Route not found' }));
```

### 6.7 RESTful API Development

**REST (Representational State Transfer)** principles:
- Resources identified by URLs (`/api/users`, `/api/users/5`)
- Stateless — each request contains all info needed
- Standard HTTP methods map to CRUD operations

| HTTP Method | CRUD | Example |
|---|---|---|
| GET | Read | `GET /api/users` — list, `GET /api/users/:id` — one |
| POST | Create | `POST /api/users` |
| PUT/PATCH | Update | `PUT /api/users/:id` (full), `PATCH` (partial) |
| DELETE | Delete | `DELETE /api/users/:id` |

**Response status codes:** `200 OK`, `201 Created`, `204 No Content`, `400 Bad Request`, `401 Unauthorized`, `403 Forbidden`, `404 Not Found`, `500 Internal Server Error`.

### 6.8 Authentication and Authorization

- **Authentication** — verifying *who* the user is (login).
- **Authorization** — verifying *what* the authenticated user is allowed to do (roles/permissions).

**JWT (JSON Web Token) based auth — common in MEAN apps:**
```javascript
const jwt = require('jsonwebtoken');
const bcrypt = require('bcrypt');

// Login route
app.post('/api/login', async (req, res) => {
  const { email, password } = req.body;
  const user = await User.findOne({ email });
  if (!user || !(await bcrypt.compare(password, user.passwordHash))) {
    return res.status(401).json({ error: 'Invalid credentials' });
  }
  const token = jwt.sign({ id: user._id, role: user.role }, process.env.JWT_SECRET, { expiresIn: '1h' });
  res.json({ token });
});

// Middleware to protect routes
function verifyToken(req, res, next) {
  const token = req.headers.authorization?.split(' ')[1];
  if (!token) return res.status(401).json({ error: 'No token provided' });
  try {
    req.user = jwt.verify(token, process.env.JWT_SECRET);
    next();
  } catch {
    res.status(403).json({ error: 'Invalid token' });
  }
}

// Role-based authorization
function requireRole(role) {
  return (req, res, next) => {
    if (req.user.role !== role) return res.status(403).json({ error: 'Forbidden' });
    next();
  };
}

app.get('/api/admin', verifyToken, requireRole('admin'), (req, res) => res.json({ secret: 'admin data' }));
```

### 6.9 Database Integration

```javascript
const mongoose = require('mongoose');
mongoose.connect(process.env.MONGO_URI);

const userSchema = new mongoose.Schema({
  name: String,
  email: { type: String, unique: true },
  passwordHash: String
});
const User = mongoose.model('User', userSchema);

app.get('/api/users', async (req, res) => {
  const users = await User.find().select('-passwordHash');
  res.json(users);
});
```

### 6.10 Sessions and Cookies

- **Cookies:** small key-value data stored in the browser, sent automatically with every request to the same domain.
- **Sessions:** server-side storage of user state, referenced by a session ID stored in a cookie.

```javascript
const session = require('express-session');

app.use(session({
  secret: 'session-secret-key',
  resave: false,
  saveUninitialized: false,
  cookie: { maxAge: 60 * 60 * 1000, httpOnly: true }   // 1 hour, JS can't access it
}));

app.post('/login', (req, res) => {
  req.session.userId = user._id;   // store in session
  res.send('Logged in');
});
```

**Sessions vs JWT:** sessions are stateful (server must store them — e.g. in Redis for scaling), JWTs are stateless (self-contained, easier to scale horizontally but harder to revoke).

### 6.11 Express.js Best Practices

- Separate concerns: routes → controllers → services → models (MVC-style folder structure).
- Use environment variables (`.env` + `dotenv`) for secrets/config, never hard-code them.
- Validate all incoming input (e.g., with `express-validator` or `joi`).
- Use `helmet` for secure HTTP headers, `cors` configured to allow only trusted origins.
- Centralize error handling; never leak stack traces to clients in production.
- Use async/await with try/catch consistently; avoid unhandled promise rejections.
- Rate-limit sensitive endpoints (e.g., `express-rate-limit`) to prevent brute-force attacks.
- Log meaningfully (e.g., `winston`/`morgan`) and monitor in production.

---

## UNIT 7: Introduction to NoSQL DB
*(10 Lectures)*

### 7.1 Introduction to NoSQL Databases

**NoSQL ("Not Only SQL")** databases store data in formats other than traditional relational tables — designed for flexibility, scalability, and handling unstructured/semi-structured data.

### 7.2 Overview of Databases (SQL vs NoSQL)

| Aspect | SQL (Relational) | NoSQL |
|---|---|---|
| Schema | Fixed, predefined | Dynamic/flexible |
| Data model | Tables with rows/columns | Documents, key-value, columnar, graph |
| Scaling | Vertical (bigger server) | Horizontal (more servers/sharding) |
| Transactions | Strong ACID compliance | Often eventual consistency (BASE model) |
| Relationships | Joins across tables | Embedding or referencing documents |
| Examples | MySQL, PostgreSQL, Oracle | MongoDB, Cassandra, Redis, Neo4j |
| Best for | Structured data, complex queries, transactions (banking) | Rapidly changing data, big data, real-time apps |

### 7.3 Advantages of NoSQL Databases

- **Flexible schema** — fields can vary between documents; easy to evolve as requirements change.
- **Horizontal scalability** — designed to scale out across many servers (sharding).
- **High performance** for large volumes of read/write, especially unstructured data.
- **Natural fit for JSON-based apps** (like MEAN) — documents map directly to JS objects.
- **Handles big data and real-time workloads** well (IoT, social media feeds, logs).

### 7.4 Types of NoSQL Databases

| Type | Description | Example |
|---|---|---|
| **Document Store** | Data stored as JSON/BSON-like documents | MongoDB, CouchDB |
| **Key-Value Store** | Simple key → value pairs, extremely fast lookups | Redis, DynamoDB |
| **Column-Family Store** | Data stored in columns rather than rows, good for analytics | Cassandra, HBase |
| **Graph Database** | Data stored as nodes and edges, good for relationships | Neo4j, ArangoDB |

### 7.5 Introduction to MongoDB

**MongoDB** is a document-oriented NoSQL database that stores data as **BSON** (Binary JSON) documents grouped into **collections** (analogous to tables).

**Terminology mapping (SQL → MongoDB):**
| SQL | MongoDB |
|---|---|
| Database | Database |
| Table | Collection |
| Row | Document |
| Column | Field |
| Primary Key | `_id` |

**Example document:**
```json
{
  "_id": "64f1a2b3c4d5e6f7a8b9c0d1",
  "name": "Bug Master",
  "email": "bugmaster@example.com",
  "skills": ["MERN", "Angular", "MongoDB"],
  "address": { "city": "Pune", "state": "Maharashtra" }
}
```

**Basic MongoDB shell/CRUD operations:**
```javascript
use myDatabase;

// Create
db.users.insertOne({ name: "Alice", age: 25 });
db.users.insertMany([{ name: "Bob" }, { name: "Carol" }]);

// Read
db.users.find();                          // all documents
db.users.find({ age: { $gt: 20 } });      // filter
db.users.findOne({ name: "Alice" });

// Update
db.users.updateOne({ name: "Alice" }, { $set: { age: 26 } });
db.users.updateMany({}, { $inc: { loginCount: 1 } });

// Delete
db.users.deleteOne({ name: "Bob" });
db.users.deleteMany({ age: { $lt: 18 } });

// Indexing (speeds up queries)
db.users.createIndex({ email: 1 }, { unique: true });
```

**Mongoose (ODM for Node.js) — schema example:**
```javascript
const mongoose = require('mongoose');

const messageSchema = new mongoose.Schema({
  sender: { type: mongoose.Schema.Types.ObjectId, ref: 'User', required: true },
  content: { type: String, required: true },
  timestamp: { type: Date, default: Date.now }
});

const Message = mongoose.model('Message', messageSchema);

// Using it
const msg = new Message({ sender: userId, content: "Hello!" });
await msg.save();

const messages = await Message.find({ sender: userId }).populate('sender', 'name email');
```

**Embedding vs Referencing (data modeling in MongoDB):**
- **Embedding:** nest related data inside a document — fast reads, good when data is accessed together and doesn't grow unbounded (e.g., an address inside a user document).
- **Referencing:** store an `_id` reference to another collection (like a foreign key) — better when data is large, shared, or changes independently (e.g., messages referencing users).

**Aggregation Framework** (for analytics-style queries):
```javascript
db.orders.aggregate([
  { $match: { status: "completed" } },
  { $group: { _id: "$customerId", total: { $sum: "$amount" } } },
  { $sort: { total: -1 } }
]);
```

---

## UNIT 8: Integrate and Deploy a MEAN App
*(5 Lectures)*

### 8.1 Integrating the Full Stack

A typical MEAN app integration flow:

```
[Angular Frontend]  --HTTP (Fetch/HttpClient)-->  [Express.js REST API]  --Mongoose ODM-->  [MongoDB]
```

**Step-by-step integration:**
1. **Design the API contract** — define endpoints, request/response shapes (e.g., `GET /api/messages`, `POST /api/messages`).
2. **Build Express routes/controllers** that query MongoDB via Mongoose models.
3. **Enable CORS** on Express so Angular (running on a different port during dev, e.g. `4200` vs `3000`) can call the API:
   ```javascript
   app.use(cors({ origin: 'http://localhost:4200' }));
   ```
4. **Create an Angular service** to call the API using `HttpClient`:
   ```typescript
   @Injectable({ providedIn: 'root' })
   export class MessageService {
     private apiUrl = 'http://localhost:3000/api/messages';
     constructor(private http: HttpClient) {}
     getMessages(): Observable<Message[]> {
       return this.http.get<Message[]>(this.apiUrl);
     }
     sendMessage(msg: Partial<Message>): Observable<Message> {
       return this.http.post<Message>(this.apiUrl, msg);
     }
   }
   ```
5. **Consume the service in a component** and bind results to the template (as covered in Unit 3).
6. **Handle environment configs** — use Angular's `environment.ts` for API base URLs (dev vs prod), and `.env` on the Node side.

### 8.2 Deployment Architecture Options

| Strategy | Description |
|---|---|
| **Single server (monolithic)** | Express serves both the API (`/api/*`) and the built Angular app (`dist/` as static files) from one Node process |
| **Separate hosting** | Angular deployed to a static host/CDN (Netlify, Vercel, S3), Express API deployed separately (Render, Railway, EC2) |
| **Containerized** | Both frontend and backend packaged as Docker containers, orchestrated via Docker Compose/Kubernetes |

**Single-server example (serving Angular from Express):**
```javascript
const path = require('path');
app.use(express.static(path.join(__dirname, 'dist/my-app')));

// API routes registered BEFORE this catch-all
app.get('*', (req, res) => {
  res.sendFile(path.join(__dirname, 'dist/my-app/index.html'));
});
```

### 8.3 Deployment Steps (typical checklist)

1. `ng build --configuration production` → generates the `dist/` folder.
2. Set environment variables (DB connection string, JWT secret, `NODE_ENV=production`) securely (never commit `.env`).
3. Choose hosting:
   - **Backend:** Render, Railway, Heroku, AWS EC2/Elastic Beanstalk, DigitalOcean.
   - **Database:** MongoDB Atlas (managed cloud MongoDB).
   - **Frontend (if separate):** Netlify, Vercel, Firebase Hosting.
4. Configure a process manager for Node in production (e.g., **PM2**) for auto-restarts and clustering:
   ```bash
   npm install -g pm2
   pm2 start server.js --name mean-app -i max   # -i max = cluster mode across CPU cores
   ```
5. Set up a reverse proxy (e.g., **Nginx**) for SSL termination, load balancing, and serving static assets efficiently.
6. Enable HTTPS (e.g., via Let's Encrypt/Certbot).
7. Set up CI/CD (e.g., GitHub Actions) to auto-build/deploy on push to `main`.
8. Monitor with logging/APM tools (e.g., PM2 monitoring, Sentry, LogRocket).

---

## Quick-Revision Cheat Sheets

### MEAN Stack at a Glance
- **M**ongoDB — NoSQL, document store, flexible schema
- **E**xpress.js — minimal Node.js backend framework, handles routing & middleware
- **A**ngular — TypeScript SPA framework, component-based
- **N**ode.js — JS runtime for the server, event-driven & non-blocking

### Angular Binding Cheat Sheet
```
{{ }}          -> interpolation (component -> view)
[prop]="val"   -> property binding
(event)="fn()" -> event binding
[(ngModel)]    -> two-way binding
*ngIf / *ngFor -> structural directives
[ngClass]/[ngStyle] -> attribute directives
```

### Express Middleware Order (typical)
```
1. express.json() / urlencoded()
2. cors()
3. helmet(), morgan() (logging/security)
4. custom auth middleware (route-specific)
5. routes
6. 404 handler
7. error-handling middleware (4 args)
```

### MongoDB Query Operators
```
$eq, $ne, $gt, $gte, $lt, $lte   -> comparison
$in, $nin                       -> membership
$and, $or, $not                 -> logical
$set, $inc, $push, $pull        -> updates
$match, $group, $sort, $lookup  -> aggregation
```

### REST + HTTP Status Codes
```
GET /resource       -> 200 OK
POST /resource       -> 201 Created
PUT/PATCH /resource/:id -> 200 OK
DELETE /resource/:id -> 204 No Content
Bad input            -> 400
Not authenticated    -> 401
Not authorized       -> 403
Not found            -> 404
Server error         -> 500
```

---
