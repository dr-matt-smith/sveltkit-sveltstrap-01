## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

```sh
# create a new project in my-app
npx sv create my-app
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```sh
# or start the server and open the app in a new browser tab
npm run dev -- --open
```

Matt notes
==========

1. create new Sveltekit project following

    https://svelte.dev/docs/kit/creating-a-project

    - `npx sv create my-app`
        - got for basic SvelteKit JS not TS


2. Add Sveltestrap following

    https://sveltestrap.js.org/?path=/docs/sveltestrap-overview--docs

    - `npm install svelte @sveltestrap/sveltestrap`

3. the bit about `+layout.svelte` from

    Add the following to `routes/+layout.svelte` to import the styles for all pages

    ```html
    <script>
        import { Styles } from '@sveltestrap/sveltestrap';
        ...
    </script>
    
    <svelte:head>
        ...
        <Styles />
    </svelte:head>
    
    ...
    ```

4. Now you can use Boostrap CSS as usual. e.g. in `+page.svelte`

    ```html
   <script>
    import { Container } from '@sveltestrap/sveltestrap';
    </script>

    <Container>
        <div class="row">
            <div class="col-sm-12">
                <h1>Welcome to SvelteKit + Sveltestrap</h1>
                <p>
                hi there, from some Bootstrap styled stuff
                </p>
            </div>
        </div>
    </Container>
    ```
   
    Note the use of Svelte compoent `Container`, rather than `<div class="container">`

    See how to use Sveltestrap compoennts at:

   - https://sveltestrap.js.org/?path=/docs/layout-container--docs
