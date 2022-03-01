---
aliases: null
date created: 2022-03-01 17:51
date updated:
---
### useInput
```jsx
import { useState } from 'react';
import { useValidation } from './useValidation';

export const useInput = (initialValue, validations) => {
  const [value, setValue] = useState(initialValue);
  const [isDirty, setIsDirty] = useState(false);
  const valid = useValidation(value, validations);
  const onChange = (e) => {
    setValue(e.target.value);
  };

  const onBlur = () => {
    setIsDirty(true);
  };
  return {
    value,
    onChange,
    onBlur,
    isDirty,
    setValue,
    setIsDirty,
    ...valid,
  };
};


```

### useValidation
```jsx
import { useEffect, useState } from 'react';

export const useValidation = (value, validations) => {
  const [isEmpty, setIsEmpty] = useState(true);
  const [minLengthError, setMinLengthError] = useState(false);
  const [emailError, setEmailError] = useState(false);
  const [telError, setTelError] = useState(false);
  const [maxLengthError, setMaxLengthError] = useState(false);
  const [inputValid, setInputValid] = useState(false);

  const textErrors = {
    name: 'Никнейм не должен содержать более 32 символов',
    email: 'Введите корректный адрес почты',
    tel: 'Номер телефона должен содержать 11 символов',
    text: 'Комментарий не должен содержать более 1000 символов',
    empty: 'Поле не может быть пустым',
    minLength: 'Слишком мало символов',
  };

  useEffect(() => {
    for (const validProp in validations) {
      switch (validProp) {
        case 'isEmpty':
          value ? setIsEmpty(false) : setIsEmpty(true);
          break;
        case 'minLength':
          value.length < validations[validProp]
            ? setMinLengthError(true)
            : setMinLengthError(false);
          break;
        case 'maxLength':
          value.length > validations[validProp]
            ? setMaxLengthError(true)
            : setMaxLengthError(false);
          break;
        case 'email':
          const reEmail =
            /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
          reEmail.test(String(value))
            ? setEmailError(false)
            : setEmailError(true);
          break;
        case 'tel':
          const reTel = /^(\+7|8)(\(\d{3}\)|\d{3})\d{7}$/;
          reTel.test(value) ? setTelError(false) : setTelError(true);
          break;
      }
    }
  }, [value]);

  useEffect(() => {
    if (isEmpty || minLengthError || emailError || telError || maxLengthError) {
      setInputValid(false);
    } else {
      setInputValid(true);
    }
  }, [isEmpty, minLengthError, maxLengthError, emailError, telError]);

  return {
    isEmpty,
    inputValid,
    minLengthError,
    emailError,
    telError,
    maxLengthError,
  };
};

```

---

###### Citation

