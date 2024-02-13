# Nuxt Storyblok bug reproduction

Enabling the `@storyblok/nuxt` module causes components to lose typings.

## Steps to reproduce

1. Install dependencies `npm install`

2. Run app `npm run dev`

3. Notice that hovering over the `<MyComponent />` within [app.vue](./app.vue) shows the type of the component

```ts
(property) MyComponent: DefineComponent<__VLS_TypePropsToRuntimeProps<{
    name: string;
}>, {}, unknown, {}, {}, ComponentOptionsMixin, ComponentOptionsMixin, ... 5 more ..., {}>
```

4. Enable/uncomment the @storyblok/nuxt module in the [nuxt config](./nuxt.config.ts)

5. Reload VSCode

6. Notice that hovering over the `<MyComponent />` within [app.vue](./app.vue) show that the component has an unknown type

```ts
(property) MyComponent: unknown
```

7. Types show up again once you disable the module and reload VSCode.
