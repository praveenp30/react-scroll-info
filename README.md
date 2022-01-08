# react-scroll-info(useScrollInfo)

![npm bundle size (version)][minzipped-badge]
[![npm version][npm-badge]][npm-version]

A custom hook for creating to access the scroll info while user scrolling on page in react components.

## Features

- You control the UI - `useScrollInfo` provides the necessary info like isPageTop, isPageBottom, isScrolledUp, isScrolledDown, scrolledPosition.

- Written in Vanilla Javascript

- Cross-browser compatibility

## Demo

[CodeSandbox demo](https://316pc.csb.app/)

## Installation

```bash
$ npm install react-scroll-info
# or
$ yarn add react-scroll-info
```

## Usage

```js
import React, { useEffect } from 'react'
import useCollapse from 'react-scroll-info'
function Demo() {
 const {
    isPageBottom,
    isPageTop,
    isScrolledDown,
    isScrolledUp,
    scrolledPosition,
    documentHeight
  } = useScrollInfo();

  useEffect(() => {
    if (isPageBottom) {
      console.log("page reached to bottom");
    }
  }, [isPageBottom]);

  return (
    <div>
    <button>
        {isScrolledDown ? 'Down' : 'Up'}
    </button>
    {
        `isPageBottom: ${isPageBottom}
        isPageTop: ${isPageTop}
        isScrolledDown: ${isScrolledDown}
        isScrolledUp: ${isScrolledUp}
        scrolledPosition: ${scrolledPosition}`
        documentHeight: ${documentHeight}`
    }
    </div>
  )
}
```
## `Detect page bottom before some pixels`

```js
import React, { useEffect } from 'react'
import useCollapse from 'react-scroll-info'
function Demo() {
 const {
    isPageBottom,
    isPageTop,
    isScrolledDown,
    isScrolledUp,
    scrolledPosition,
    documentHeight
  } = useScrollInfo(50); // isPageBottom return true before 50 pixels of page bootm.

  useEffect(() => {
    if (isPageBottom) {
      console.log("page reached to bottom");
    }
  }, [isPageBottom]);

  return (
    <div>
    <button>
        {isScrolledDown ? 'Down' : 'Up'}
    </button>
    </div>
  )
}
```

## `useScrollInfo` Config

The following are optional properties passed into `useScrollInfo()`:


| Param                 | Type     | Default                        | Description                                                                                                                                         |
| -------------------- | -------- | ------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| param1           | number  | 0                    | If you want detect pagebottom before some pixels, pass param1 by default it 0.                                                                                                                |


## What you get

| Name             | Description                                                                                                 |
| ---------------- | ----------------------------------------------------------------------------------------------------------- |
| isPageBottom | User reached bottom of the page it returns true - Boolean                       |
| isPageBottom   | User reached top of the page it returns true - Boolean              |
| isScrolledUp       | User scrolling Up it returns true -    Boolean                                  |
| isScrolledDown      | User scrolling Down it returns true -    Boolean                                                          |
| scrolledPosition      | Current scrolled position - Number
| documentHeight      | Document(page) Height - Number