[![Build Status](https://dev.azure.com/prabhummurthy/react-chrono/_apis/build/status/prabhuignoto.react-chrono?branchName=master)](https://dev.azure.com/prabhummurthy/react-chrono/_build/latest?definitionId=7&branchName=master)
[![DeepScan grade](https://deepscan.io/api/teams/10074/projects/13644/branches/234929/badge/grade.svg)](https://deepscan.io/dashboard#view=project&tid=10074&pid=13644&bid=234929)
[![Codacy Badge](https://app.codacy.com/project/badge/Grade/f2e24a98defd4e4fa7f6f24d86b8dab5)](https://www.codacy.com/manual/prabhuignoto/react-chrono?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=prabhuignoto/react-chrono&amp;utm_campaign=Badge_Grade)
[![Language grade: JavaScript](https://img.shields.io/lgtm/grade/javascript/g/prabhuignoto/float-menu.svg?logo=lgtm&logoWidth=18)](https://lgtm.com/projects/g/prabhuignoto/float-menu/context:javascript)
![Snyk Vulnerabilities for GitHub Repo](https://img.shields.io/snyk/vulnerabilities/github/prabhuignoto/react-chrono?style=flat)
[![Depfu](https://badges.depfu.com/badges/48a23a6a830309649b7e516467cd9a48/overview.svg)](https://depfu.com/github/prabhuignoto/react-chrono?project_id=15325)

![logo](./readme-assets/social-logo-small.png)

![slideshow](./readme-assets/demo.gif)

**Try it on CodeSandbox!**

[![Edit react-chrono](https://codesandbox.io/static/img/play-codesandbox.svg)](https://codesandbox.io/s/react-chrono-bg56e?fontsize=14&hidenavigation=1&theme=dark)

<h2>Features</h2>

- 🚥 Render timelines in three different modes ([Horizontal](#-getting-started), [Vertical](#vertical-mode), [Tree](#tree-view)).
- 🌲&nbsp; Use the [Tree](#tree-view) mode to layout the timeline cards vertically in a tree like fashion.
- 📺&nbsp; Auto play the timeline with the [slideshow](#slideshow-mode) prop.
- ⌨&nbsp; Navigate the timelines via Keyboard.
- 🎨&nbsp; [Customize](#theme) colors with ease.
- 💪&nbsp; Built with [Typescript](https://www.typescriptlang.org/)

<h2>Table of Contents</h2>

- [⚡ Installation](#-installation)
- [🚀 Getting Started](#-getting-started)
  - [Vertical Mode](#vertical-mode)
  - [Tree View](#tree-view)
  - [Slideshow Mode](#slideshow-mode)
- [Props](#props)
  - [Mode](#mode)
  - [⌨ Keyboard Navigation & Disabling it](#-keyboard-navigation--disabling-it)
  - [Slideshow Mode](#slideshow-mode-1)
  - [Title Position](#title-position)
  - [Item Width](#item-width)
  - [🎨 Theme](#-theme)
- [📦Build Setup](#build-setup)
- [🔨 Contributing](#-contributing)
- [🧱 Built with](#-built-with)
- [🔭 What's coming next](#-whats-coming-next)
- [Meta](#meta)

## ⚡ Installation

```sh
yarn install react-chrono
```

## 🚀 Getting Started

Please make sure you wrap the component in a container that has a `width` and `height`. When no `mode` is specified, the component defaults to `HORIZONTAL` mode.

Use the `items` prop to create the timeline. Each Timeline item have the following properties.

`title`, `contentTitle`, `contentText`, `contentDetailedText`

Here is an example Timeline with minimal settings.

```sh
  const items = [{
    title: "May 1940",
    contentTitle: "Dunkirk",
    contentText:"Men of the British Expeditionary Force (BEF) wade out to a destroyer during the evacuation from Dunkirk.",
    contentDetailedText: "On 10 May 1940, Hitler began his long-awaited offensive in the west...",
  }, ...];

  <div style={{ width: "500px", height: "400px" }}>
    <chrono items={items} />
  </div>
```

![app-home](./readme-assets/app-home.png)

### Vertical Mode

To render the timeline vertically use the `VERTICAL` mode

```sh
  <div style={{ width: "500px", height: "950px" }}>
    <chrono
      items={items}
      mode="VERTICAL"
    />
  </div>
```

### Tree View

In `Tree` mode the timeline is rendered vertically with cards alternating between left and right sides.

```sh
  <div style={{ width: "500px", height: "950px" }}>
    <chrono
      items={items}
      mode="TREE"
    />
  </div>
```

![app-tree](./readme-assets/app-tree.png)

### Slideshow Mode

Play the timeline automatically with the `slideShow` mode.

```sh
  <div style={{ width: "500px", height: "950px" }}>
    <chrono
      items={items}
      slideShow
      mode="TREE"
    />
  </div>
```

![tree-slideshow](./readme-assets/vertical_slideshow.gif)

## Props

| name              | description                                                                           | default      |
| ----------------- | ------------------------------------------------------------------------------------- | ------------ |
| mode              | sets the layout for the timeline component. can be `HORIZONTAL`, `VERTICAL` or `TREE` | `HORIZONTAL` |
| items             | collection of timeline items                                                          | []           |
| disableNavOnKey   | prop to disable keyboard navigation.                                                  | false        |
| slideShow         | starts the timeline in slideshow mode.                                                | false        |
| slideItemDuration | The amount of delay in `ms` for the timeline points in `slideshow` mode.              | 2500         |
| titlePosition     | sets the position of the title in `HORIZONTAL` mode. can be `TOP` or `BOTTOM`.        | `TOP`        |
| itemWidth         | width of the timeline section in `HORIZONTAL` mode.                                   | 300          |
| theme             | prop to customize the colors.                                                         | 300          |

### Mode

`react-chrono` supports three modes `HORIZONTAL`, `VERTICAL` and `TREE`. The mode prop can be used to define the orientation of the cards.

### ⌨ Keyboard Navigation & Disabling it

The timeline by default can be navigated via keyboard.

- For `HORIZONTAL` mode use your <kbd>LEFT</kbd> <kbd>RIGHT</kbd> arrow keys for navigation.
- For `VERTICAL` or `TREE` mode, the timeline can be navigated via the <kbd>UP</kbd> <kbd>DOWN</kbd> arrow keys.
- To easily jump to the first item or the last item in the timeline, use <kbd>HOME</kbd> or <kbd>END</kbd> key.

The keyboard navigation can be completely disabled by setting the `disableNavOnKey` to true.

```sh
<chrono items={items} disableNavOnKey />
```

### Slideshow Mode

Slideshow can be enabled by setting the `slideShow` prop to true. You can also set an optional `slideItemDuration` that sets the time delay between cards.

```sh
<chrono items={items} slideShow slideItemDuration={4500} />
```

### Title Position

This setting only applies for the `HORIZONTAL` mode. The prop `titlePosition` sets the position of the individual titles to either `TOP` or `BOTTOM`.

```sh
<chrono items={items}  titlePosition="BOTTOM" />
```

### Item Width

The `itemWidth` prop can be used to set the width of each individual timeline sections. This setting is applicable only for the `HORIZONTAL` mode.

### 🎨 Theme

Customize colors with `theme` prop.

```sh
<chrono items={items}  titlePosition="BOTTOM" theme={{primary: "red", secondary: "blue" }} />
```

## 📦Build Setup

``` bash
# install dependencies
yarn install

# start dev setup
yarn run start

# run css linting
yarn run lint:css

# package lib
yarn run rollup
```

## 🔨 Contributing

1. Fork it ( [https://github.com/prabhuignoto/react-chrono/fork](https://github.com/prabhuignoto/react-chrono/fork) )
2. Create your feature branch (`git checkout -b new-feature`)
3. Commit your changes (`git commit -am 'Add feature'`)
4. Push to the branch (`git push origin new-feature`)
5. Create a new Pull Request

## 🧱 Built with

- [React JS](react) - The Component is written in React and [Typescript](typescript).
- [styled-components](styled-components) - The Component is written in React and [Typescript](styled-components).

## 🔭 What's coming next

- Support for Mobile devices & Tablets (responsive).
- Polished UI control for navigating the timeline.
- Support for embedding images in the timeline.

## Meta

Prabhu Murthy – [@prabhumurthy2](https://twitter.com/prabhumurthy2) – prabhu.m.murthy@gmail.com

Distributed under the MIT license. See `LICENSE` for more information.

[https://github.com/prabhuingoto/](https://github.com/prabhuingoto/)

<!-- Markdown link & img dfn's -->

[react]: https://reactjs.org
[typescript]: https://typescriptlang.org
[styled-components]: https://styled-components.com/
