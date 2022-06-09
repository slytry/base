---
aliases: 
tags: 
date created: Thursday, April 7th 2022, 2:54:26 pm
date modified: Thursday, June 9th 2022, 7:59:14 pm
title: Transition
---

# Transition
Компонент Transition позволяет описать переход от одного состояния компонента к другому с течением времени с помощью простого декларативного API. Чаще всего он используется для анимации монтажа и демонтажа компонента, но также может использоваться для описания переходных состояний на месте.

Transition - базовый компонент библиотеки. Если что то обернуть в него, то станет возможно отслеживать четыре состояния и в момент наступления каждого из них применять анимацию

```jsx
import { Transition } from 'react-transition-group';

const duration = 300;

const defaultStyle = {
  transition: `opacity ${duration}ms ease-in-out`,
  opacity: 0,
}

const transitionStyles = {
  entering: { opacity: 1 },
  entered:  { opacity: 1 },
  exiting:  { opacity: 0 },
  exited:  { opacity: 0 },
};

const Fade = ({ in: inProp }) => (
  <Transition in={inProp} timeout={duration}>
    {state => (
      <div style={{
        ...defaultStyle,
        ...transitionStyles[state]
      }}>
        I'm a fade Transition!
      </div>
    )}
  </Transition>
);
```

### Состояния

- `'entering'`
- `'entered'`
- `'exiting'`
- `'exited'`

### Опции

#### nodeRef



---

###### Citation

- [Transition](https://reactcommunity.org/react-transition-group/transition)
