# L7 Lab downloads

0.1.10: чтение показателей через экспортированный cache provider CarSupport1.78. Из установленного APK установлены точные ContentResolver.call методы request_property/get_property с Bundle property:int и ответом property/area/status/value_type/value/car_ts/seq/received_at. Собственная реализация, без заимствования vendor-кода.

Установить поверх предыдущей версии → Диагностика → Показатели машины · проверка → Проверить через CarSupport на 30 секунд → Home. После теста Сохранить архив чтения и передать Download/L7Lab/l7lab-telemetry-<timestamp>.zip. Числа сверить с LiDashboard.

Сначала используется существующий свежий кэш; при отсутствии свежего значения регистрируется запрос данного ID (не более одного за сессию). Семь прежних whitelisted IDs, poll1сек, наш таймер30сек. Важное ограничение CarSupport: API отмены запроса нет, ID остаются в его process-lifetime списке до перезапуска процесса. Это не гарантирует завершение producer CMA при остановке нашего теста.

Системные автомобильные permissions и optional Car SDK libraries больше не запрашиваются. Никаких put_property, setters, Settings writes, подмены UID/подписи или изменения лицензии. Отбрасываются неверные ID/area/status/типы, нечисловые/NaN/out-of-range значения и кэш старше5сек.

Локально проверен оригинальный неизменённый provider DEX в отдельном UID; только cache producer синтетический. Проверены exact request/get/get_requested,7заявок без повторов, native card, NaN/stale,30сек остановка нашего polling и report-only ZIP. Фактическое получение чисел на машине через CMA пока не проверено.

Публикуются только собственный APK и страница. Извлечённые DEX, оригинальные приложения, тестовый fixture, архивы машины и результаты с частными данными не публикуются.
