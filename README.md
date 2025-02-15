MosZooLib
Этот проект представляет собой библиотеку для управления зоопарком, где используются принципы SOLID для создания гибкой и поддерживаемой архитектуры.

Принципы SOLID в проекте
1. Single Responsibility Principle (Принцип единственной ответственности)
Каждый класс в проекте имеет одну ответственность:

Animal: Базовый класс для всех животных, отвечает за хранение информации о еде и здоровье.

Herbo: Класс для травоядных животных, добавляет функциональность для измерения уровня доброты.

Predator: Абстрактный класс для хищников, расширяет базовый класс Animal.

Zoo: Управляет коллекцией животных и вещей, обеспечивает методы для добавления и получения данных.

VetClinic: Отвечает за проверку здоровья животных.

2. Open/Closed Principle (Принцип открытости/закрытости)
Классы открыты для расширения, но закрыты для модификации:

Animal: Базовый класс, который можно расширять, создавая новые типы животных (например, Monkey, Rabbit, Tiger, Wolf).

Herbo и Predator: Абстрактные классы, которые можно расширять для создания новых видов животных.

3. Liskov Substitution Principle (Принцип подстановки Барбары Лисков)
Классы-наследники могут использоваться вместо базовых классов без изменения поведения программы:

Herbo и Predator могут использоваться везде, где ожидается Animal.

VetClinic реализует интерфейс IHealthChecker, что позволяет легко заменить его на другую реализацию.

4. Interface Segregation Principle (Принцип разделения интерфейса)
Интерфейсы в проекте узконаправленные:

IAlive: Определяет только свойства, связанные с жизнью (например, Food).

IHealthChecker: Определяет метод для проверки здоровья животного.
5. Dependency Inversion Principle (Принцип инверсии зависимостей)
Классы зависят от абстракций, а не от конкретных реализаций:

Zoo зависит от интерфейса IHealthChecker, а не от конкретной реализации VetClinic.

Примеры классов
Животные
Monkey: Обезьяна, травоядное животное.

Rabbit: Кролик, травоядное животное.

Tiger: Тигр, хищник.

Wolf: Волк, хищник.

Вещи
Thing: Базовый класс для вещей в зоопарке.

Ветеринарная клиника
VetClinic: Проверяет здоровье животных.

