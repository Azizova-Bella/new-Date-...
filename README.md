# Руководство: Date, Map и Set в JavaScript

![image](https://github.com/user-attachments/assets/87e2803e-a6b5-4d30-b8a3-94197b90226b)


## Введение
JavaScript предоставляет мощные встроенные структуры данных, которые упрощают работу с датами, коллекциями пар ключ-значение и наборами уникальных элементов. Это руководство подробно объясняет, как использовать объекты `Date`, `Map` и `Set` в повседневной практике разработки.

---

![image](https://github.com/user-attachments/assets/394717e3-a062-4b16-8437-a516296c12e1)


## Объект Date
Объект `Date` используется для представления моментов времени и выполнения операций с датами. Он работает на основе миллисекунд, прошедших с 1 января 1970 года (времени Unix).

### Создание объекта Date
```javascript
// Текущая дата и время
const now = new Date();

// Определённая дата
const specificDate = new Date('2025-01-01T12:00:00');

// Указание года, месяца, дня, часа и минут
const anotherDate = new Date(2025, 0, 1, 12, 0, 0);

console.log(now);
console.log(specificDate);
console.log(anotherDate);
```

### Получение компонентов даты
```javascript
const date = new Date();
console.log('Год:', date.getFullYear());
console.log('Месяц (0-11):', date.getMonth());
console.log('День месяца:', date.getDate());
console.log('Часы:', date.getHours());
console.log('Минуты:', date.getMinutes());
console.log('Секунды:', date.getSeconds());
```

### Преобразование и сравнение дат
```javascript
const date1 = new Date('2025-01-01');
const date2 = new Date('2025-01-02');

console.log(date1 < date2); // true
console.log(date1.toISOString()); // 2025-01-01T00:00:00.000Z
```

---

![image](https://github.com/user-attachments/assets/3786413a-cd5a-4a05-b920-4211d71a3777)

## Объект Map
`Map` предоставляет способ хранения ключей любого типа, включая объекты.

### Создание и добавление пар ключ-значение
```javascript
const map = new Map();
map.set('name', 'Alice');
map.set(42, 'Answer');
map.set(true, 'Truthy value');

console.log(map);
```

### Получение, удаление и проверка элементов
```javascript
console.log(map.get('name')); // Alice
console.log(map.has(42));    // true
map.delete(true);
console.log(map.size);       // 2
```

### Перебор элементов Map
```javascript
map.forEach((value, key) => {
  console.log(`Ключ: ${key}, Значение: ${value}`);
});

for (const [key, value] of map) {
  console.log(`Ключ: ${key}, Значение: ${value}`);
}
```

---

![image](https://github.com/user-attachments/assets/a35328f7-9597-4f8d-8408-caba06bf6577)

## Объект Set
`Set` используется для хранения уникальных значений любого типа.

### Создание и добавление значений
```javascript
const set = new Set();
set.add(1);
set.add(2);
set.add(2); // Игнорируется, так как уже добавлено

console.log(set); // Set { 1, 2 }
```

### Проверка, удаление и получение размера
```javascript
console.log(set.has(1)); // true
set.delete(1);
console.log(set.size);   // 1
```

### Перебор элементов Set
```javascript
set.forEach(value => {
  console.log(value);
});

for (const value of set) {
  console.log(value);
}
```

---

![image](https://github.com/user-attachments/assets/13a9258e-983c-46a2-92be-d71689c41c23)

## Сравнение Map и Set

| Свойство        | Map                                | Set                                |
|-----------------|------------------------------------|------------------------------------|
| Хранение       | Пары ключ-значение                 | Уникальные значения               |
| Тип ключей     | Любой                             | ---                                |
| Доступ         | По ключу                          | ---                                |
| Перебор        | forEach, for...of, entries()      | forEach, for...of                 |

---

## Примеры использования

### Подсчёт слов в тексте с помощью Map
```javascript
const text = 'JavaScript Map Map JavaScript Set';
const words = text.split(' ');

const wordCount = new Map();
words.forEach(word => {
  const count = wordCount.get(word) || 0;
  wordCount.set(word, count + 1);
});

console.log(wordCount);
```

### Удаление дублирующихся значений из массива с помощью Set
```javascript
const numbers = [1, 2, 2, 3, 3, 3, 4, 5, 5];
const uniqueNumbers = Array.from(new Set(numbers));

console.log(uniqueNumbers); // [1, 2, 3, 4, 5]
```

---

![image](https://github.com/user-attachments/assets/94a394c9-b765-4cfd-9af2-7981d0d960c2)

## Заключение
Объекты `Date`, `Map` и `Set` являются ключевыми инструментами для работы с данными в JavaScript. Они облегчают решение задач, связанных с временными метками, коллекциями и уникальными наборами. Используйте их, чтобы писать более чистый и эффективный код!

