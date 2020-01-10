# react-native-startups-practices
React Native Tips, Notes and best practices

# Welcome to React Native Mansion - My personal tips!

Hi! I'm James Jara, and this is my personal checklist that I use in **React Native Mansion**. If you want to learn about my point of view, you can read me.


# Name Convention

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
      "everything-else",
      "render",
    ],
  }],
```

## Methods

- Methods that return JSX starts with render `renderItem`
- Methods that executes an actions starts with on `onLogout`

# React Native Pull Request

Since working on many react native products I have seen many many leads always strugulling with the PR contrinutions from the other developers, I have been creating this template that can be applied to bitbucket or github.

## XXX
 
