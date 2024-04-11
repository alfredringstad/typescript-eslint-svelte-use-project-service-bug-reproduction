# typescript-eslint-svelte-use-project-service-bug-reproduction

This is a reproduction case to show the issue with `EXPERIMENTAL_useProjectService` and `extraFileExtensions`.

To try it out, first run `npm i` and then `npm run lint` and see how the following linter error is returned:

```
/.../typescript-eslint-svelte-use-project-service-bug-reproduction/src/App.svelte
  5:5  error  "var" scope should not extend outside the reactive block(invalid_var_declaration)  svelte/valid-compile
```

Note that this is a symptom of the fact that the code is transpiled to ES5, as a result of a default tsconfig being applied when the correct one cannot be found.

Change `EXPERIMENTAL_useProjectService` to false in `eslint.config.js` and run `npm run lint` again. We no longer get any linting error.
 