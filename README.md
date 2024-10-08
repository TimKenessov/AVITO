Обзор проекта
Этот проект автоматизирует UI-тестирование веб-приложения с использованием Selenium WebDriver и Python. Тесты предназначены для взаимодействия с элементами на веб-странице, навигации с использованием пагинации, фильтрации элементов по категориям и возврата на главную страницу после выполнения действий. Тесты структурированы с использованием pytest и Allure для отчетности.

Структура проекта
Проект состоит из следующих файлов:

1. base_page.py: Содержит класс BasePage, который предоставляет общие методы для взаимодействия с элементами страницы. Включает методы для проверки наличия элементов, кликабельности и видимости.

2. elements_page.py: Содержит класс ElementsPage, который наследуется от BasePage и реализует методы для выполнения специфичных действий на странице элементов, таких как фильтрация по категории, возврат на главную страницу и навигация с помощью пагинации.

3. elements_locators.py: Содержит класс ElementsPageLocators, который определяет локаторы для элементов страницы, используемые в тестах.

4. test_elements_page.py: Содержит тесты для проверки функциональности веб-приложения. Используются методы из ElementsPage и локаторы из ElementsPageLocators для выполнения тестов и проверок.

Установка и запуск
1. Установка зависимостей:
pip install - r requirements.txt

2. Запуск тестов
   Для запуска всех тестов выполните команду pytest --alluredir=allure-results
   Для запуска 1 теста выполните команду pytest -m filter_by_category_test --alluredir=allure-results1
   Для запуска 2 теста выполните команду pytest -m back_to_main_test --alluredir=allure-results2
   Для запуска 3 теста выполните команду pytest -m navigate_by_pagination_test --alluredir=allure-results3

   Для просмотра отчетов Allure выполните:
   allure serve allure-results (для всех тестов)
   allure serve allure-results1 (для 1 теста)
   allure serve allure-results2 (для 2 теста)
   allure serve allure-results3 (для 3 теста)

Описание методов
BasePage:

open(): Открывает указанную URL-адрес.
element_is_present(locator, timeout): Проверяет наличие элемента на странице.
elements_are_present(locator, timeout): Проверяет наличие всех элементов по указанному локатору.
element_is_clickable(locator, timeout): Проверяет, что элемент доступен для клика.
ElementsPage:

filter_by_category(): Выбирает категорию из раскрывающегося списка.
return_to_the_main_page(): Возвращается на главную страницу и проверяет отображение основного контента.
navigate_using_pagination(): Перемещается по страницам результатов поиска с помощью пагинации.
Локаторы
Локаторы для элементов на странице определяются в elements_locators.py. Они используются в тестах для поиска и взаимодействия с элементами на веб-странице.

Тесты
test_filter_by_category: Проверяет фильтрацию по категории и убедитесь, что выбранный элемент отображается.
test_return_to_the_main_page: Проверяет возврат на главную страницу и отображение основного контента.
test_navigate_using_pagination: Проверяет переход между страницами с помощью пагинации.
Примечания
Если тесты не пройдут с первого раза, пожалуйста повторите попытку 
