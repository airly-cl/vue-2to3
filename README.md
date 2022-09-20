# Vue2to3

Vue2.x libraries aren't Vue3-compatible in most cases. This is due to a plethora of breaking changes introduced in Vue 3.0, which means most Vue2 components will be a pain in the ass to implement in newer projects. This library can help ease such pains.

## Creating a library

1. Copy and paste the original library's `/src` to Vue2to3's rootdir.
2. Change the name section of `package.json` to reflect your new lib's desired name (`your-lib`). Remember to use kebab-case (a.k.a. anticucho-case 🇨🇱).

3. Add all of your library's dependencies and peer-dependencies in the `package.json` file.

4. Run the `npm install` command to install Rollup and its components.

5. Add any and all needed components to the exports section of `components.js`.

6. Run the `npm run build` command. When completed, a `/dist` is created.

7. You're done! Install your new lib by running `npm install path/to/your-lib`. There is also the possibility of publishing it to npm.


## Using the new library

Add `your-lib` as a plugin in your app's entrypoint (likely `main.js` or `index.js`):

```
import yourLib from 'your-lib'

const app = createApp(App).use(router)
  .use(yourLib)
```

Use your new components in any of your app's Vue templates (`.vue` files):

```
import 'your-lib/dist/library.css'
import { ComponentOne, ComponentTwo } from 'your-lib'

... 

<ComponentOne ... /> 
<ComponentTwo ... /> 
```