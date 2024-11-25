| Ідентифікатор та назва атаки (вразливості)                | Вимога (FR, NFR)                                                                                                     | Приклад вразливостей, які може використовувати атака                                                                 | Приклад запобігання успішної реалізації атаки                                                                 |
|-----------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| A01: Broken Access Control (Порушення доступу)            | FR-02: Створення списку працівників, FR-03: Налаштування показників якості                                        | Невірна обробка прав доступу дає змогу неавторизованим користувачам змінювати або переглядати дані інших працівників.  | Впровадження політики контролю доступу, що базується на ролях (RBAC) для кожної операції в системі.              |
| A02: Cryptographic Failures (Помилки в криптографії)       | NFR-02: Шифрування даних користувачів, NFR-05: Постійний доступ до системи                                        | Відсутність шифрування персональних даних може спричинити витік важливої інформації у разі атаки на систему.          | Використання сучасних шифрувальних алгоритмів, таких як AES і RSA, для захисту даних.                           |
|                                                           |                                                                                                                      | Використання слабких шифрів або неналежна конфігурація SSL/TLS з'єднань.                                             | Регулярне оновлення версій SSL/TLS і аудит налаштувань безпеки.                                               |
| A03: Injection (SQL, NoSQL, OS, LDAP Injection)            | FR-01: Створення користувацького обліку, FR-06: Оновлення показників якості                                        | Використання SQL-ін'єкцій під час реєстрації може дати зловмиснику доступ до даних усіх користувачів.                | Впровадження підготовлених запитів (Prepared Statements) і використання ORM для захисту від SQL-ін'єкцій.      |
|                                                           |                                                                                                                      | Використання уразливих полів введення для ін'єкцій, що дає змогу маніпулювати даними без належної перевірки.         | Валідація всіх вхідних даних і застосування підготовлених запитів для взаємодії з базою даних.                 |
| A04: Insecure Design (Ненадійне проектування)              | FR-04: Налаштування умов для обчислень, NFR-04: Простота використання інтерфейсу                                   | Ненадійний дизайн може призвести до неправильних налаштувань умов для розрахунку показників, що порушує точність.      | Використання перевірених методів проектування та ретельний аналіз вимог на етапі планування.                   |
|                                                           |                                                                                                                      | Поганий UX/UI дизайн може призвести до помилок користувачів при налаштуванні параметрів або обчисленнях.              | Проведення юзабіліті-тестування і дотримання принципів зручного дизайну.                                      |
| A05: Security Misconfiguration (Неправильна конфігурація безпеки) | NFR-05: Постійний доступ до системи                                                                                  | Невірна конфігурація серверів або бази даних може сприяти виникненню вразливостей, що використають зловмисники.        | Регулярне оновлення конфігурацій ПЗ і серверів, застосування рекомендованих налаштувань безпеки.               |
| A06: Vulnerable and Outdated Components (Застарілі компоненти) | NFR-03: Підтримка одночасного доступу до 100 користувачів                                                              | Використання застарілих компонентів може призвести до проблем з ефективністю або безпекою через відомі вразливості.    | Регулярне оновлення всіх бібліотек, компонентів і фреймворків для підтримки безпеки та надійності.               |
| A07: Identification and Authentication Failures (Помилки ідентифікації та автентифікації) | FR-01: Створення облікових записів                                                                                     | Відсутність належної автентифікації дозволяє зловмисникам реєструвати фальшиві облікові записи та отримувати доступ до даних. | Використання багатофакторної автентифікації та надійних паролів для всіх користувачів.                          |
| A08: Software and Data Integrity Failures (Порушення цілісності ПЗ та даних) | NFR-01: Генерація звітів за короткий проміжок часу                                                                     | Застаріле або пошкоджене програмне забезпечення може вплинути на точність даних, що генеруються для звітів.             | Використання механізмів перевірки цілісності даних і контрольних сум для захисту від помилок.                  |
| A09: Security Logging and Monitoring Failures (Помилки в логуванні та моніторингу безпеки) | NFR-05: Постійний доступ до системи                                                                                  | Відсутність належного моніторингу може дозволити атакам проходити непомітно впродовж тривалого часу.                   | Встановлення автоматичних сповіщень про аномальні дії та проведення постійного моніторингу безпеки.            |
| A10: Server-Side Request Forgery (SSRF) (Запити на стороні сервера) | FR-05: Генерація звітів у форматі Excel                                                                               | SSRF може дозволити зловмиснику отримати доступ до внутрішніх систем під час створення або обробки звітів.            | Обмеження доступу до внутрішніх служб і ретельна перевірка запитів, що надходять на сервер.                    |