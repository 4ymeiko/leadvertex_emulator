Эмулятор шаблонизатора сайта LeadVertex.Ru
===================

Эмулятор шаблонизатора сайта LeadVertex.Ru для быстрой и удобной верстки лендингов прямо у себя на компьютере.

При использовании учитывайте, что эмулятор есть эмулятор. Он не использует тот же самый код что и шаблонизатор LeadVertex, а лишь повторяет его поведение

В папке "templates" находятся каталоги с лендингами. Каждый каталог - отдельный лендинг. В каждом каталоге автоматически будет создан файл config.xml, в котором
будут прописаны все параметры для данного лендинга, такие как поля формы, цена товара и прочие. В файле много комментариев, так что вопросов возникнуть не должно

#### Требования
Apache + PHP 5.4+
Для запуска у себя на компьютере мы рекомендуем платформу http://open-server.ru/

#### Что нового в версии 4.0?

Формы заказа в новом формате. Поддержка старого формата будет прекращена в скором времени. Для подробного ознакомления рекомендуем обратиться к документации.

- http://demo-1.leadvertex.info/demo.html - полностью настроенной формы заказа
- http://demo-1.leadvertex.info/landing.html - рекомендация по переносу лендингов
- http://demo-1.leadvertex.info/docs.html - документация

#### Что нового в версии 3.43?

- Поддержка тега {{order_total}}, который возвращает итоговую стоимость оформленного заказа пользователя

#### Что нового в версии 3.40?

- Поддержка тегов {{utm_source}}, {{utm_medium }}, {{utm_term}}, {{utm_content}}, {{utm_campaign}}, которые возвращают переданныве в url UTM-метки

#### Что нового в версии 3.36?

- В папке files демо-лендинга включен файл .htaccess, который необходим для подключения шрифтов при использовании тарифов с FTP. Рекомендуем использовать его во всех лендингах
- В отладочной панели теперь выбран текущий лендинг

#### Что нового в версии 3.34?

- возможность использовать javascript-методы ```window.leadvertex.form.*``` для формы уточнения заказа, указывая вместо номера формы строку ```'update'```

#### Что нового в версии 3.31?

- возможность использования эмулятора на хостинге. Для этого в файле index.php измените значение константы ```define('TEMPLATE',false)``` на ```define('TEMPLATE','имя_каталога_с_лендингом')```;
- шаблонизатор будет требовать обновления только по реальной необходимости

#### Что нового в версии 3.3?

- Форма уточнения заказа ```{{form_update}}```. Используется для уточнения данных заказа на страницах success и однокликовых апселов. Подробнее в документации
- Исправлена ошибка в выпадающем поле количества товаров: в значение value у тега ```<option>``` использовался префикс "шт."

#### Что нового в версии 3.2?

- Добавлены гео-теги ```{{geo_country}}``` и ```{{geo_country_code}}``` (используются для реализации гео-таргетинга через js)
- Добавлены математические операчии для ```{{price_total}}```. Например, ```{{price_total-300}}```

#### Что нового в версии 3.1?

- Теперь можно подключать любую версию jQuery. Конфликтов не будет. Тег ```{{jquery}}``` остался как и прежде, но теперь его не обязательно использовать

#### Что нового в версии 3.0?

- Вместо корневого файла index.html теперь должен быть файл layout.html (исправьте везде. Совместимость c index.html на LeadVertex будет еще в течении двух месяцев)
- Тулбар для отладки лендингов. Теперь если лендинг содерджит недопустимые имена файлов и каталогов, вы это увидите.
- Возможность легкого переключения между лендингами. Теперь в папке templates каждый лендинг хранится в отдельной папке
- Возможность задать индивидуальные настройки формы и цены для каждого лендинга. При первом открытии лендинга в его папке будет создан файл config.xml который задает все настройки
- Возможность скачать лендинг как *.tar
- Минимальная версия PHP 5.4

#### Что нового в версии 2.5?

- поддержка ценовых опций ```{{price_multi}}```, ```{{price-option additional1="значение"}}```

#### Что нового в версии 2.4?

- ```{{no_layout}}``` - если этот тег прописан в коде страницы из папки pages/, то содержимое этой страницы будет отображено само по себе, т.е. без использования главного файла index.html. Пример можете посмотреть на странице успешного заказа
- ```{{form|no_css}}``` - При отображении формы заказа к ней автоматически подключаются некоторые стили. В большинстве случаев эти стили нужны чтобы не стилизовать форму «с нуля». Однако иногда некоторые из них (например, border и box-sizing: border-box;) могут мешать. Чтобы исключить мешающие стили, подключайте форму прописывая модификатор no_css. С указанием номеров формы аналогично {{form_2|no_css}}
- Корневой index.html больше не является обязательным. Если этого файла нет, то будет рендериться содержимое страницы из pages/ целиком
- Глобально обновлен демо-лендинг