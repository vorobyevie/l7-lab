# L7 Lab downloads

0.1.9: прямое чтение семи vendor-сигналов через установленный Android Car property manager под обычным UID L7 Lab. Прежний LASS route исключён из пользовательского теста: сервер1.13.0 содержит только map передачи и не поддерживает эти семь ID.

Установить поверх предыдущей версии → Диагностика → Показатели машины · проверка → Проверить показатели на 30 секунд → Home. После теста Сохранить архив чтения и передать Download/L7Lab/l7lab-telemetry-<timestamp>.zip для разбора.

В APK объявлены read-side vendor permissions; подпись/привилегии этим не выдаются. Отчёт фиксирует реальные granted-флаги и protectionLevel шести связанных разрешений, ошибки API/сервиса по каждому сигналу. Установленные shared libraries optional; в AOSP без Android Car приложение сообщает отсутствие API. Никакого повышения привилегий, setter, произвольных ID и автозапуска; команды стеклу отсутствуют.

Локальные тесты используют синтетические public API signatures Car.createCar/getCarManager/getProperty/CarPropertyValue: lifecycle, числа, unavailable, permission denial, 30-секундный timeout, disconnect, нативный View в другом UID и отчёт-only ZIP. Это не подтверждает фактическую совместимость OEM client library или выдачу чисел в машине.

Публикуются только собственный APK и страница. Чужие программы, архивы автомобиля и локальные test fixture не публикуются.
