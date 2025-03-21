## Диаграмма классов для задания Практика «CVS»

![дк csv](https://github.com/user-attachments/assets/57b64d62-3cec-4864-a561-a85e80584b1e)

### Описание основных сущностей:
- *CloneVersionSystem*: Это основная система, управляющая версиями клонов. Она реализует интерфейс ICloneVersionSystem и предоставляет методы для выполнения операций над клонами. Основные функции включают:

  - Execute(string query): Метод, который принимает строку запроса и выполняет соответствующую операцию над клоном (обучение, откат, переобучение, клонирование, проверка).

- *ICloneVersionSystem*: Интерфейс, который определяет контракт для CloneVersionSystem. Он содержит метод Execute.

- *ImmutableStack<T>*: Класс, реализующий неизменяемый стек. Он используется для хранения последовательности программ, усвоенных клоном, и истории откатов. Ключевые операции:

  - Push(T value): Добавляет элемент на вершину стека, возвращая новый экземпляр стека.

  - Pop(): Удаляет верхний элемент стека, возвращая новый экземпляр стека.

  - Peek(): Возвращает верхний элемент стека без удаления.

  - IsEmpty: Возвращает true, если стек пуст.

- *CloneState*: Класс, представляющий состояние клона. Он хранит:

  - Programs: ImmutableStack<string> - стек программ, усвоенных клоном.

  - Rollbacks: ImmutableStack<string> - стек истории откатов программ.
