# начало работы с программой

1. Распаковать архив в удобное место
2. В файле `settings/settings.json` заполнить почту и ключ программы.
3. Заполнить [параметры](params.md) в файлах запуска

## файлы запуска

### ozon

- В строке `--companyid id ^` заменить `id` на id вашей компании
- [Выгрузить куки файл](cookies.md) в папку settings

```text
main.exe ^
--ozon ^
--void ^
--companyid id ^
--probabilistic ^
--file settings/prob.json ^
--fromstar 4 ^
--everyminutes 30 ^
--shortsleep 0.5 ^
--brand brandname ^
--cookies settings/seller.ozon.ru_cookies.json
pause
```

### wildberries

Заменить в строке `--apikey token ^` `token` на апи токен с доступом на чтение и редактирование отзывов.

```text
main.exe ^
--wildberries ^
--void ^
--apikey token ^
--probabilistic ^
--file settings/prob.json ^
--fromstar 4 ^
--everyminutes 30 ^
--shortsleep 0.5 ^
pause
```

### добавление параметров

для удобства параметры добавляются каждый на новую строку.
В конце каждой строки, кроме строки перед pause необходимо ставить `^`.
Этот символ позволяет склеить строки в одну для создания команды запуска.
