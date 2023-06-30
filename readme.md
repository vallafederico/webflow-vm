
# How To

## Run the scripts
This thing is using pnpm.

From the terminal to the side (create a new one if doesn't exist). 
Make sure other terminals are not runing.

To run the **dev server** you can run `pnpm dev`.
To run the **build** you can run `pnpm build`.

From the new tasks, you can alternatively start a **dev** or **build** task.

Assuming you're using the file structure correctly, you should import and run things from the `index.js` file at the root of the poroject.


This means the terminal, when running, is going to give a link that looks something like this: `https://localhost:5173`.
If you click on it, you'll get to an empty webpage. Add `/index.js` to the webpage you see, and you shuld see your script.
Copy and paste it as the `src` parameter of a script tag.

```html
<script defer src="{YOUR WEB PAGE ADDRESS}"></script>
```

## Install dependencies

Use [NPMJS](https://www.npmjs.com/) to find the name of what you want to install. Once you have the name.

Open a terminal instance on the side. 
If you already have a terminal running kill the current process using `ctrl+c`

Type `pnpm i` + the *name* of the package. *(ie `pnpm i gsap`)*

On the npm page look for the instruction on how to import (specifically if it has `{}` or not).
Import the dependency only in the file (or files) you need it in.
```js
import gsap from 'gsap
```

## Import and export files

You can import and export functions from different files in your project. 
To export, the file should have something to export in it.

```js

// |- /src/something.js
export function something() {}

// |- /index.js
import {someting} from './src/something.js'

```

---

`./` in the path means the root of the project.

To link something that's on a lower level vs where you currently are, 
you can so `../` to go out a level.

```js

// |- /index.js
export function something() {}

// |- /src/something.js
import {someting} from '../something.js' // this pulls from the enclosing folder

```
