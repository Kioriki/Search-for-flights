### **Особенности приложения:**

- Работа с фейковым серверным *API* с помощью `async-thunk`.
- Сортировка билетов по цене, длительности перелёта и количеству пересадок.
- Фильтрация по авиакомпаниям.
- Фильтрация по количеству пересадок.

Вы можете использовать любой формат данных, но он должен поддерживать сортировку.

**Пример сущности, приходящей из *API* эталонного задания:**

    `export interface TicketTime {
        startTime: string;
        endTime: string;
    }

    export interface Ticket {
        id: number;
        **from**: string;
        **to**: string;
        company: string;
        price: number;
        currency: 'RUB';
        **time**: TicketTime;
        duration: number;
        date: string;
        connectionAmount: number | null;
    }`

Чтобы создать заготовку проекта, воспользуйтесь *Vite* и выберите пресет `react-ts` или `react-swc-ts`:

`npm create vite@latest` или `yarn create vite`

Также для создания проекта вы можете использовать Create React App, но с сентября 2022 года утилита больше не поддерживается разработчиками. Это не означает, что CRA больше нельзя пользоваться, однако, в настоящее время предпочтительнее использовать Vite для новых проектов. К тому же, последняя утилита активно поддерживается, отлично работает с React и позволяет намного быстрее собирать проекты.

## **КРИТЕРИИ ОЦЕНИВАНИЯ**

Всего за проект можно получить **10 баллов**.

### **Функциональные требования:**

1. Проект создан с помощью *Vite* или *Create React App*, исправно запускается с помощью команды `npm start` или `npm run dev` и собирается с помощью `npm run build`.
    - Полностью удовлетворяет — **2 балла**.
    - Частично удовлетворяет — **1 балл** (проект собирается с ошибками).
    - Не удовлетворяет — **0 баллов**.
2. Проект использует *Redux Toolkit*, не использует стандартный *Redux* с `createStore`, не использует легаси-методы `connect`, `mapStateToProps`, `mapDispatchToProps`.
    - Полностью удовлетворяет — **2 балла**.
    - Частично удовлетворяет — **1 балл** (проект исправно работает, но использует старый *API*).
    - Не удовлетворяет — **0 баллов**.
3. Требования к адаптивной вёрстке — приложение в целом соответствует макету. Версии для ПК и мобильных устройств исправно работают.
    - Полностью удовлетворяет — **2 балла**.
    - Частично удовлетворяет — **1 балл** (неправильная работа на одной из версий, сильное несоответствие макету).
    - Не удовлетворяет — **0 баллов**.
4. Используются дополнительные методы из *Redux Toolkit*, такие как `createAsyncThunk` для запросов к *API*, `createEntityAdapter` для работы с массивами данных.
    - За каждый дополнительный метод — **1 балл**.
5. Проект написан на *TypeScript*:
    - Полностью удовлетворяет — **2 балла**.
    - Не удовлетворяет — **0 баллов**.

Макет Figma - https://www.figma.com/file/NYQS9wMdCJazJaVfFiMv5W/Tickets-Redux-Task?type=design&node-id=0-1&mode=design&t=EcCPvae3lLhZ523I-0

-В проекте использован фэйковый API => server-json. 
-Репозиторий на server-json => https://github.com/Kioriki/json-server-for-search-aviatickets

КАК ЗАПУСТИТЬ ПРОЕКТ?
1. Клонируем этот репозиторий.
2. Клонируем этот репозиторий - https://github.com/Kioriki/json-server-for-search-aviatickets.git
3. Открываем папку из репозитория "json-server-for-search-aviatickets" в VS Code.
4. Открываем терминал и пишем следующие команды: 
    4.1. npm add json-server
    4.2. npm start и открываем ссылку "http://localhost:4000/tickets"
5. Не закрывая это окно VS Code, Открываем в новом окне папку из репозитория "Search-For-Flights" и вводим следующие команды:
    5.1. npm i (npm install)
    5.2. npm start