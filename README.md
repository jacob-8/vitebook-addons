# Vitebook Addons

`npm i -D vitebook-addons`

An [addon](https://vitebook.dev/guides/addons.html) for [Vitebook](https://vitebook.dev) published using [SvelteKit packaging](https://kit.svelte.dev/docs#packaging).

`Knobs.svelte` component modeled after [Svench knobs](https://svench-docs.vercel.app/_/Usage/knobs)


 Pass knobs properties (boolean, string, number, or range) to the `input` prop access values from `let:output`. Typescript provides autocompletion for the proper properties on the way out. I prefer to use the shortcut notation as documented in the [Svench knobs docs](https://svench-docs.vercel.app/_/Usage/knobs#knobs-passed-as-plain-objects-shortcut-notation) with the type of the knob being inferred from it.

Range knobs can be declared using a default value matching the format `${minValue}${maxValue};${initialValue}` (e.g., `-10-10;5`).



## Usage

```js
import { Knobs } from 'vitebook-addons';

<Knobs input={{ myBool: false, myNum: 10, myStr: 'hello', myRange: '-10-10;5' }} let:output={{myBool, myNum, myStr, myRange}}>
  <MyComponent>{myBool},{myNum},{myStr},{myRange}</MyComponent>
</Knobs>
  ```


## TODO
Though full object notation works as seen in the Svench docs, the type interface will be incorrect. If someone has a compelling use case for full object notation, they can help me know how to improve the use of Generics and types through the `knobs.ts` file to achieve such.
