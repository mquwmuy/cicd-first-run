
# Практическая работа — CI/CD

## Первый запуск

Настроен workflow Lesson CI. Все 4 теста прошли.
Сайт собран, артефакт lesson-site скачан и проверен.
В release.json указан SHA исходного коммита.

Успешный запуск:
https://github.com/mquwmuy/cicd-first-run/actions/runs/43495601153

## Ошибка

Прогноз: при замене style.css на missing.css
тест завершится ошибкой, сборка и сохранение
артефакта будут пропущены.

Красный запуск:
https://github.com/mquwmuy/cicd-first-run/actions/runs/43496537419

SHA: 5d39286a6ab4254f66a3fdff3449113966445616

Тест: test_stylesheet_exists

Ошибка:
Missing stylesheet: missing.css

Результат: тест упал, Build site и Save site artifact
пропущены. Прогноз подтвердился.

## Исправление

Восстановлена ссылка на style.css.
Все 4 теста успешно прошли, сайт собран.

Зелёный запуск:
https://github.com/mquwmuy/cicd-first-run/actions/runs/43496890344

SHA: 6d20e28ccbf7700f8a369e21e16e88ad5b083016

## Изменение аудитории

Аудитория изменена с 301 на 302 отдельным коммитом.

Прогноз: тесты пройдут, поскольку не проверяют
номер аудитории.

Результат: все 4 теста прошли.

Запуск:
https://github.com/mquwmuy/cicd-first-run/actions/runs/43497182692

## Вывод

Тесты выполняются на GitHub runner.
Логи и артефакты сохраняются на GitHub.
Ошибка теста останавливает сборку.
Зелёный CI не гарантирует отсутствие всех ошибок,
так как тесты проверяют только заданные условия.

Источник: mdvwork/ci-cd-practice-for-3-course.
При оформлении использовалась помощь ChatGPT.
