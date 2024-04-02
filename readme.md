# USE-STATE

- useState - bu sizning komponentingizga holat o'zgaruvchisini qo'shish imkonini beruvchi React Hook.

Code:

```
const [state, setState] = useState(initialState)

```

- Holat o'zgaruvchisini e'lon qilish uchun komponentingizning yuqori darajasidagi useStateni chiqarib olish kerak

```
import { useState } from 'react';

function MyComponent() {
  const [age, setAge] = useState(28);
  const [name, setName] = useState('Taylor');
  const [todos, setTodos] = useState(() => createTodos())};
```

# USE-REF

- useRef - bu renderlash uchun kerak bo'lmagan qiymatga murojaat qilish imkonini beruvchi React Hook.

```
const ref = useRef(initialValue)
```

- Ref e'lon qilish uchun komponentingizning yuqori darajasidagi useRef ni chiqarib olish kerak.

```
import { useRef } from 'react';

function MyComponent() {
  const intervalRef = useRef(0);
  const inputRef = useRef(null);}

```

# USE-EFFECT

- useEffect - bu komponentni tashqi tizim bilan sinxronlash imkonini beruvchi React Hook.

```
useEffect(setup, dependencies?)
```

- useEffect e'lon qilish uchun komponentingizning yuqori darajasidagi useEffect ni chiqarib olish kerak.


```
import { useEffect } from 'react';
import { createConnection } from './chat.js';

function ChatRoom({ roomId }) {
  const [serverUrl, setServerUrl] = useState('https://localhost:1234');

  useEffect(() => {
    const connection = createConnection(serverUrl, roomId);
    connection.connect();
    return () => {
      connection.disconnect();
    };
  }, [serverUrl, roomId]);
  // ...
}
```