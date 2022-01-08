# react-scroll-info(useScrollInfo)

[![NPM](https://nodei.co/npm/react-scroll-info.png)](https://nodei.co/npm/react-scroll-info/)

A custom hook for creating to access the scroll info while user scrolling on page in react components.

## Features

- You control the UI - `useScrollInfo` provides the necessary info like isPageTop, isPageBottom, isScrolledUp, isScrolledDown, scrolledPosition, documentHeight

- Written in Vanilla Javascript

- Cross-browser compatibility

## Demo

[CodeSandbox Demo](https://316pc.csb.app/)

## Installation

```bash
$ npm install react-scroll-info
# or
$ yarn add react-scroll-info
```

## Usage

```js
import React, { useEffect } from 'react'
import useScrollInfo from 'react-scroll-info'
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
        {isScrolledDown ? 'Up' : 'Down'}
    </button>
    {
        `isPageBottom: ${isPageBottom}
        isPageTop: ${isPageTop}
        isScrolledDown: ${isScrolledDown}
        isScrolledUp: ${isScrolledUp}
        scrolledPosition: ${scrolledPosition}
        documentHeight: ${documentHeight}`
    }
    </div>
  )
}
```
## `Detect Page Bottom Before Some Pixels`

```js
import React, { useEffect } from 'react'
import useScrollInfo from 'react-scroll-info'
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
        {isScrolledDown ? 'Up' : 'Down'}
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
| isPageBottom | Reached bottom of the page it returns true - Boolean                       |
| isPageBottom   | Reached top of the page it returns true - Boolean              |
| isScrolledUp       | Scrolling Up it returns true -    Boolean                                  |
| isScrolledDown      | Scrolling Down it returns true -    Boolean                                                          |
| scrolledPosition      | Current scrolled position - Number
| documentHeight      | Document(page) Height - Number