 ---
tags: 
aliases: тесты 
date created: Saturday, March 26th 2022, 7:37:44 pm
date modified: Monday, June 20th 2022, 4:48:42 pm
---

# Automatic test

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

###### References

 - [Unit Testing Components in Storybook](https://dev.to/jenc/unit-testing-components-in-storybook-oc7)
 - [Storybook ❤️ Testing Library](https://medium.com/storybookjs/storybook-%EF%B8%8F-testing-library-f5fd63e106a0)
 - [Jest](https://jestjs.io/en/) https://github.com/YauhenKavalchuk/useful/blob/main/front-end-2022.md
