---
aliases: null
date created: 2022-03-04 16:15
date updated:
---

Unit тесты нужны нужны чтобы убедиться, что определенные входные данные производят определенные выходные данные таким образом, который поддается автоматическому тестированию. 

Для этого мы создадим модульные тесты, используя библиотеку тестирования React и @storybook/testing-react.

Мы может повторно переиспользовать историю для теста.

В данном случае Unit тест проверяем UI, в релльной жизни такой тест оказывается хрупким. Для тестирования отображения лучше использовать ручное тестирование, snapshot и визуальную регрессия

src/components/TaskList.test.js

```js
import { render } from '@testing-library/react';

import { composeStories } from '@storybook/testing-react';

import * as TaskListStories from './TaskList.stories'; //👈  Our stories imported here

//👇 composeStories will process all information related to the component (e.g., args)
const { WithPinnedTasks } = composeStories(TaskListStories);

it('renders pinned tasks at the start of the list', () => {
  const { container } = render(<WithPinnedTasks />);

  expect(
    container.querySelector('.list-item:nth-child(1) input[value="Task 6 (pinned)"]')
  ).not.toBe(null);
});
```

---

###### Citation

- [React Testing Library](https://testing-library.com/docs/react-testing-library/intro/)