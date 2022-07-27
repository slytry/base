---
aliases: 
tags: 
date created: Wednesday, July 27th 2022, 9:32:17 am
date modified: Wednesday, July 27th 2022, 9:48:40 am
---

# RadioGroup

Радиокнопки позволяют пользователям выбирать один вариант из списка взаимоисключающих вариантов. Все возможные варианты отображаются заранее, чтобы пользователи могли их сравнить.

| 1                                     | 2                                     |
| ------------------------------------- | ------------------------------------- |
| ![[Pasted image 20220727093408.png ]] | ![[Pasted image 20220727093435.png ]] |

## Signature

```tsx
function Example() {
  let [selected, setSelected] = React.useState('yes');

  return (
      <RadioGroup
        label="Are you a wizard? (controlled)"
        value={selected}
        onChange={setSelected}
      >
        <Radio value="yes">Yes</Radio>
        <Radio value="no">No</Radio>
      </RadioGroup>
  );
}
```

## RadioGroup props

| NAME         | TYPE | DEFAULT    | DESCRIPTION                         |
| ------------ | ---- | ---------- | ----------------------------------- |
| children     |      |            |                                     |
| orientation  |      | 'vertical' |                                     |
| name         |      |            |                                     |
| value        |      |            | The current value (controlled)      |
| defaultValue |      |            | The default value (uncontrolled)    |
| label        |      |            | The content to display as the label |
|              |      |            |                                     |

---

###### References

- [RadioGroup](https://react-spectrum.adobe.com/react-spectrum/RadioGroup.html)
