# структура программы

- main.exe - основная программа.
- [ozon.cmd](startfiles.md#ozon) - скрипт для запуска программы в режиме работы с ozon. Можно переименовывать и создавать свои.
- [wildberries.cmd](startfiles.md#wildberries) - скрипт для запуска программы в режиме работы с wildberries. Можно переименовывать и создавать свои.
- responderbot.cer - сертификат, с помощью которого подписана программа. Если на программу ругается антивирус, то можно попробовать добавить этот сертификат в доверенные или просто добавить программу в доверенные.
- settings
    - prob.json - шаблоны ответов для вероятностного режима.
    - list.json - шаблоны ответов для режима выбора из списка.
    - settings.json - файл с настройками программы.
