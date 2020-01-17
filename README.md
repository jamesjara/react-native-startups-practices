# react-native-startups-practices
React Native Tips, Notes and best practices

# Welcome to React Native Mansion - My personal tips!

Hi! I'm James Jara, and this is my personal checklist that I use in **React Native Mansion**. If you want to learn about my point of view, you can read me.


# A) Name Convention

This section defines some JavaScript and React Native naming conventions, which are split into several sections.

## Eslint
- Adding this configuration to your `.eslintrc` will allow your mind to read any code in the same pattern, this will create a code pattern. Remember to install `sort-comp`.

```
 "react/sort-comp": [1, {
    "order": [
      "type-annotations",
      "static-methods",
      "static-variables",
      "instance-variables",
      "lifecycle",
      "/^on.+$/",
      "/^render.+$/",
      "everything-else",
      "render",
    ],
  }],
```

## Methods

- Methods that return JSX starts with render `renderItem`
- Methods that executes an actions starts with on `onLogout`

# B) React Native Pull Request

Since working on many react native products I have seen many many leads always strugulling with the PR contrinutions from the other developers, I have been creating this template that can be applied to bitbucket or github.

```
 * [] I am affirming this is my best work ever. 

## Working on multiplatform implementations:

* [ ] Upload gif/SS from Android implementation.
* [ ] Upload gif/SS from iOS implementation.

## Working on components:

* [ ] Add the story book implementation.
* [ ] Upload gif/SS from story book implementation.

## Quality

* [ ] No new warnings in tests, storybook, eslint, package check.
* [ ] I test the suite case for this specific task.

## Unit testing

* [ ] Upload the new coverage in the description.
* [ ] Keep up to 50% of coverage.
* [ ] Add snapshot tests specially for components.

## Adding and Updating Packages? (If applicable)

* [ ] Explain an elaborate the package.
* [ ] Add to the packages list.

## Extra

* [ ] methods that returns JSX starts with `render`.
* [ ] methods that execute action starts with `on`.
```

# C) Scaffolding

This structure can be different that many of my other products, in this document I'm presenting this one just because of a matter of personal preference, but based on keeping a clean way to structure testing, styles, strings, continuous integration, etc :).

```
.
├── __mocks__
│   └── @enhancers
├── __tests__
│   └── __snapshots__
├── android
├── ios
├── server
│   ├── entities
│   ├── example
│   └── trips
├── src
│   ├── components
│   │   ├── Input
│   │   │   ├── __stories__
│   │   │   └── __tests__
│   │   │       └── __snapshots__
│   ├── config
│   ├── constants
│   │   ├── actions-types
│   │   ├── api
│   │   ├── colors
│   │   ├── images
│   │   ├── reducers-names
│   │   ├── routes
│   │   ├── schemas
│   │   ├── strings
│   │   └── typings
│   ├── enhancers
│   │   └── withKeyboardView
│   ├── navigation
│   ├── screens
│   │   ├── Global
│   │   │   ├── Auth
│   │   │   │   ├── Home
│   │   │   │   ├── Login
│   │   │   │   └── Register
│   │   │   ├── Boot
│   │   │   └── Home
│   │   └── ActivityFeed
│   ├── services
│   │   ├── navigation
│   │   └── permissions
│   └── state
│       ├── entities
│       └── global
│           └── auth
└── storybook
```

# D) Coding preferences

- Prefer using `PureComponen`t instead of `Component` to use shallow rendering.
- Do not mix types like using a JSX as a boolean.
- NavigationOptions goes at screens.
- Prefer singular alias when importing all, in this way it seems to make more sense when used later on.
```import * as color from '@constants/colors';
console.log(color.RED);
```
