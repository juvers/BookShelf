<div>
  <h1 align="center"><a href="https://epicreact.dev">Build an Epic React App 🚀 EpicReact.Dev</a></h1>
  <strong>
    Building a full React application
  </strong>
  <p>
    The React and JavaScript ecosystem is full of tools and libraries to help
    you build your applications. In this (huge) workshop we’ll build an
    application from scratch using widely supported and proven tools and
    techniques. We’ll cover everything about building frontend React
    applications, from the absolute basics to the tricky parts you'll run into
    building real world React apps and how to create great abstractions.
  </p>

  <a href="https://epicreact.dev">
    <img
      alt="Learn React from Start to Finish"
      src="https://kentcdodds.com/images/epicreact-promo/er-1.gif"
    />
  </a>
</div>

<hr />

<!-- prettier-ignore-start -->
[![Build Status][build-badge]][build]
[![All Contributors][all-contributors-badge]](#contributors)
[![GPL 3.0 License][license-badge]][license]
[![Code of Conduct][coc-badge]][coc]
<!-- prettier-ignore-end -->

## Prerequisites

- You'll want experience with React before going through this material. The
  lessons get progressively more advanced. Once you hit something you're
  unfamiliar with, that's your cue to go back and review the other parts of
  EpicReact.Dev.

## System Requirements

- [git][git] v2.13 or greater
- [NodeJS][node] `^10.13 || 12 || 14`
- [npm][npm] v6 or greater

All of these must be available in your `PATH`. To verify things are set up
properly, you can run this:

```shell
git --version
node --version
npm --version
```

If you have trouble with any of these, learn more about the PATH environment
variable and how to fix it here for [windows][win-path] or
[mac/linux][mac-path].

## Setup

> If you want to commit and push your work as you go, you'll want to
> [fork](https://docs.github.com/en/free-pro-team@latest/github/getting-started-with-github/fork-a-repo)
> first and then clone your fork rather than this repo directly.

After you've made sure to have the correct things (and versions) installed, you
should be able to just run a few commands to get set up:

```
node setup
```

This may take a few minutes.

If you get any errors, please read through them and see if you can find out what
the problem is. If you can't work it out on your own then please [file an
issue][issue] and provide _all_ the output from the commands you ran (even if
it's a lot).

If you can't get the setup script to work, then just make sure you have the
right versions of the requirements listed above, and run the following commands:

```
npm install
npm run validate
```

It's recommended you run everything locally in the same environment you work in
every day, but if you're having issues getting things set up, you can also set
this up using [GitHub Codespaces](https://github.com/features/codespaces)
([video demo](https://www.youtube.com/watch?v=gCoVJm3hGk4)) or
[Codesandbox](https://codesandbox.io/s/github/kentcdodds/bookshelf).

## Running the app

To get the app up and running (and really see if it worked), run:

```shell
npm start
```

This should start up your browser. If you're familiar, this is a standard
[react-scripts](https://create-react-app.dev/) application.

You can also open the production deployment:
[bookshelf.lol](https://bookshelf.lol).

## Running the tests

```shell
npm test
```

This will start [Jest](https://jestjs.io/) in watch mode. Read the output and
play around with it. The tests are there to help you reach the final version,
however _sometimes_ you can accomplish the task and the tests still fail if you
implement things differently than I do in my solution, so don't look to them as
a complete authority.

## Working through the exercises

To get started, run:

```shell
node go
```

This will allow you to choose which exercise you want to work on. From there,
open the `INSTRUCTIONS.md` file and follow the instructions.

If you'd like to work on an extra credit, but you want to skip the preceding
steps, you can run `node go` again:

```shell
node go
```

This will let you choose the next exercise or you can choose which part of the
exercise you'd like to work on. This will update your `exercise` files to the
correct version for you to work on that extra credit.

### Exercises

The exercises are in different branches. Each branch changes the
`INSTRUCTIONS.md` file to contain instructions you need to complete the
exercise.

The purpose of the exercise is **not** for you to work through all the material.
It's intended to get your brain thinking about the right questions to ask me as
_I_ walk through the material.

### Helpful Emoji 🐨 💪 🏁 💰 💯 🦉 📜 💣 👨‍💼 🚨

Each exercise has comments in it to help you get through the exercise. These fun
emoji characters are here to help you.

- **Kody the Koala** 🐨 will tell you when there's something specific you should
  do
- **Matthew the Muscle** 💪 will indicate what you're working with an exercise
- **Chuck the Checkered Flag** 🏁 will indicate that you're working with a final
  version
- **Marty the Money Bag** 💰 will give you specific tips (and sometimes code)
  along the way
- **Hannah the Hundred** 💯 will give you extra challenges you can do if you
  finish the exercises early.
- **Olivia the Owl** 🦉 will give you useful tidbits/best practice notes and a
  link for elaboration and feedback.
- **Dominic the Document** 📜 will give you links to useful documentation
- **Berry the Bomb** 💣 will be hanging around anywhere you need to blow stuff
  up (delete code)
- **Peter the Product Manager** 👨‍💼 helps us know what our users want
- **Alfred the Alert** 🚨 will occasionally show up in the test failures with
  potential explanations for why the tests are failing.

### Workflow

- Checkout the exercise branch
- Read through the `INSTRUCTIONS.md`
- Start exercise
- Go through every mentioned file and follow the instructions from the emoji
- We all come back together
- I go through the solution and answer questions
- Move on to the next exercise.
- Repeat.

### App Data Model

- User

  - id: string
  - username: string

- List Item

  - id: string
  - bookId: string
  - ownerId: string
  - rating: number (-1 is no rating, otherwise it's 1-5)
  - notes: string
  - startDate: number (`Date.now()`)
  - finishDate: number (`Date.now()`)

> For convenience, our friendly backend engineers also return a `book` object on
> each list item which is the book it's associated to. Thanks backend folks!

> /me wishes we could use GraphQL

If your "database" gets out of whack, you can purge it via:

```javascript
window.__bookshelf.purgeUsers()
window.__bookshelf.purgeListItems()
```

- Book

  - id: string
  - title: string
  - author: string
  - coverImageUrl: string
  - pageCount: number
  - publisher: string
  - synopsis: string

## Troubleshooting

<details>
  
  <summary>Running "node go" does not list any branches</summary>
  
This means there was something wrong when you ran the setup. Try running:

```
node ./scripts/track-branches.js
```

If you're still not getting the branches, then you can do this manually:

```
git branch --track "exercises/01-bootstrap" "origin/exercises/01-bootstrap"
git branch --track "exercises/02-styles" "origin/exercises/02-styles"
git branch --track "exercises/03-data-fetching" "origin/exercises/03-data-fetching"
git branch --track "exercises/04-authentication" "origin/exercises/04-authentication"
git branch --track "exercises/05-routing" "origin/exercises/05-routing"
git branch --track "exercises/06-cache-management" "origin/exercises/06-cache-management"
git branch --track "exercises/07-context" "origin/exercises/07-context"
git branch --track "exercises/08-compound-components" "origin/exercises/08-compound-components"
git branch --track "exercises/09-performance" "origin/exercises/09-performance"
git branch --track "exercises/10-render-as-you-fetch" "origin/exercises/10-render-as-you-fetch"
git branch --track "exercises/11-unit-testing" "origin/exercises/11-unit-testing"
git branch --track "exercises/12-testing-hooks-and-components" "origin/exercises/12-testing-hooks-and-components"
git branch --track "exercises/13-integration-testing" "origin/exercises/13-integration-testing"
git branch --track "exercises/14-e2e-testing" "origin/exercises/14-e2e-testing"
git pull --all
```

</details>


<!-- markdownlint-enable -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->





<!-- prettier-ignore-start -->
[npm]: https://www.npmjs.com/
[node]: https://nodejs.org
[git]: https://git-scm.com/
[build-badge]: https://img.shields.io/github/workflow/status/kentcdodds/bookshelf/validate/main?logo=github&style=flat-square
[build]: https://github.com/kentcdodds/bookshelf/actions?query=workflow%3Avalidate
[license-badge]: https://img.shields.io/badge/license-GPL%203.0%20License-blue.svg?style=flat-square
[license]: https://github.com/kentcdodds/bookshelf/blob/main/LICENSE
[coc-badge]: https://img.shields.io/badge/code%20of-conduct-ff69b4.svg?style=flat-square
[coc]: https://github.com/kentcdodds/bookshelf/blob/main/CODE_OF_CONDUCT.md
[emojis]: https://github.com/kentcdodds/all-contributors#emoji-key
[all-contributors]: https://github.com/kentcdodds/all-contributors
[all-contributors-badge]: https://img.shields.io/github/all-contributors/kentcdodds/bookshelf?color=orange&style=flat-square
[win-path]: https://www.howtogeek.com/118594/how-to-edit-your-system-path-for-easy-command-line-access/
[mac-path]: http://stackoverflow.com/a/24322978/971592
[issue]: https://github.com/kentcdodds/bookshelf/issues/new
<!-- prettier-ignore-end -->
