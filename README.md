# react-native-startups-practices
React Native Tips, Notes and best practices

# Welcome to React Native Mansion - My personal tips!

Hi! I'm James Jara, and this is my personal checklist that I use in **React Native Mansion**. If you want to learn about my point of view, you can read me.


# A) Name Convention.

This section defines some JavaScript and React Native naming conventions, which are split into several sections.

## Eslint.
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

## Methods.

- Methods that return JSX starts with render `renderItem`
- Methods that executes an actions starts with on `onLogout`

# B) React Native Pull Request.

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

# C) Scaffolding.

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

# D) Coding preferences.

- Prefer using `PureComponen`t instead of `Component` to use shallow rendering.
- Do not mix types like using a JSX as a boolean.
- NavigationOptions goes at screens.
- Prefer singular alias when importing all, in this way it seems to make more sense when used later on.
`import * as color from '@constants/colors'; console.log(color.RED);`


# E) GIT, Workflow Model.

One phrase, the power of branches, as well a few other rules to keep or git log beatifull and clean.

## General GIT Rules.
- Daily Pull Request reviews at 11:00 AM.
- Prefer `rebase` over `merge`.
- Keep enviroment clean, delete merged branches.
- Merge strategy for merge features branches into develop `git merge --squash`.

## Main Branches.
- Master: highly stable branch, it is always production-ready.
- Staging: derived from the develop, used for pre-release testing.
- Develop: derived from the master, used for integrating different feature branches.

## Temporary Branches.
- Feature: specific development.
- Hotfix: derived from master branch, it fixes a bug in production and it's merged into master and develop.

## Conventional Commits ( + JIRA ).
- Prefer enforcing properly formatted commit messages.
- Commit messages must meet the conventional commit format. [conventionalcommits](https://www.conventionalcommits.org/en/v1.0.0/).
- Commit message must include the JIRA project and JIRA Id task.
```
git commit -m "SA-1001: fix(login) - Fixed bug on foo"
git commit -m "SA-1001: feat(profile) - Adds new form"
git commit -m "SA-1001: chore - Updated README"
git commit -m "SA-1001: feat(ui) - Added dark theme"
```
# F) Continuos integretion and deployment.

Another one quick phrase, agility with faster feedback. 

## Continuos integretion ( + Bitbucket Pipelines ).
- Enforcing clean and success builds on branches.
- Protecting your hard-earned code coverage.
```
image: node:10.15.3
pipelines:
  default:
    - step:
        caches:
          - node
        script:
          - yarn
          - yarn run lint
          - yarn run test:package
          - yarn run test
```

## Continuos Deployment ( + Bitrise ).


 
  



