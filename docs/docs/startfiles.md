# начало работы с программой

1. Распаковать архив в удобное место
2. В [файле](settings.md) `settings/settings.json` заполнить почту и лицензионный ключ.
3. Заполнить [параметры](params.md) в файлах запуска
4. Заполнить [файл для составления ответов](generators.md).

## файлы запуска

### ozon

- В строке `--companyid id ^` заменить `id` на id вашей компании
- [Выгрузить куки файл](cookies.md) в папку settings

#### файл запуска

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

#### файл запуска

```bat
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

### avito

Заменить `Client_secret` и `Client_id` на свои которые можно получить [тут](https://www.avito.ru/professionals/api)

#### файл запуска

```text
main.exe ^
--avito ^
--void ^
--apikey Client_secret ^
--companyid Client_id ^
--probabilistic ^
--file settings/prob.json ^
--fromstar 4 ^
--everyminutes 30 ^
--shortsleep 0.5 ^
pause
```

### avito chat

* Заменить `Client_secret` и `Client_id` на свои которые можно получить [тут](https://www.avito.ru/professionals/api)
* Задать параметры `--old` и `--new`. Тогда программа будет отвечать только на отзывы в диапазоне `[now - old, now - new]`
* Для данного режима рекомендуется выбирать режим `--fromlist` и в шаблоне заполнить

Так как сообщения в чате не являются отзывами, оценка у них будет `0` и статус `normal`.
Поэтому для адекватного поведения, предалагается использовать следующий шаблон для генерации ответа.

```json
{
    "normal": {
        "0": [
            "Ответ для чата. Например все операторы сейчас заняты, мы ответим в ближайшее время."
        ],
    },
    "stop_words" : [
    ]
}
```

#### файл запуска

```text
main.exe ^
--avitochat ^
--void ^
--apikey Client_secret ^
--companyid Client_id ^
--fromlist ^
--file settings/list.json ^
--fromstar 4 ^
--everyminutes 30 ^
--shortsleep 0.5 ^
--old old ^
--new new
pause
```

### добавление параметров

для удобства параметры добавляются каждый на новую строку.
В конце каждой строки, кроме строки перед pause необходимо ставить `^`.
Этот символ позволяет склеить строки в одну для создания команды запуска.
