
# How To

## Run the scripts
This thing uses pnpm.

From the terminal to the side (create a new one if doesn't exist), you'll be able to run scripts, install dependency, and build everything into a single script.

Before doing everything else, when stasrting a new project, run `pnpm install`.

To run the **dev server** you can run `pnpm dev`.
To run the **build** you can run `pnpm build`.

(From the new tasks, you can alternatively start a **dev** or **build** task.)

Assuming you're using the file structure correctly, you should import and run things from the `index.js` file at the root of the project.

When Running `pnpm dev` a page containint your files will open to the right.
As default, it should have both an `index.js` and an `index.js.map`. If you click on the file you want (the .js one),
in the top bar you'll have a *URL* you'll be able to paste inside a `<script>` tag in your webflow project.

To make sure everything runs correctly and as smooth as possible

```html
<!-- This is the basic version-->
<!-- in /body-->
<script src="{THE URL FROM THE TOP BAR}"></script>

<!-- This is the SUGGESTED version-->
<!-- in /head-->
<script defer src="{THE URL FROM THE TOP BAR}"></script>
```

## Install dependencies

Use [NPMJS](https://www.npmjs.com/) to find the name of what you want to install. Once you have the name.

Open a terminal instance on the side. 
If you already have a terminal running kill the current process using `ctrl + c`

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
