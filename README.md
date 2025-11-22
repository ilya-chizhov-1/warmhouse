# Project_template

Это шаблон для решения проектной работы. Структура этого файла повторяет структуру заданий. Заполняйте его по мере работы над решением.

# Задание 1. Анализ и планирование

<aside>

Чтобы составить документ с описанием текущей архитектуры приложения, можно часть информации взять из описания компании и условия задания. Это нормально.

</aside

### 1. Описание функциональности монолитного приложения

**Управление отоплением:**

- Пользователи могут запросить список сенсоров: GET /api/v1/sensors
- Система поддерживает CRUD операции для сенсоров
- Система поддерживает изменение значение и статус сенсора: PATCH /api/v1/sensors/:id/value

**Мониторинг температуры:**

- Пользователи могут запросить температуру по локации: GET /api/v1/sensors/temperature/:location

### 2. Анализ архитектуры монолитного приложения

- Стек: приложение на Go, компилируется и упаковывается Docker-образ.
- Хранилище: PostgreSQL.
- Архитектура: Монолитная, все компоненты системы (обработка запросов, бизнес-логика, работа с данными) находятся в рамках одного приложения.

### 3. Определение доменов и границы контекстов

- Sensors: получают данные от сервера и управляют отоплением.
- Customer: запрос температуры и управление отоплением.
- Telemetry: управляет сенсорами, взаимодействует с пользователем.
- Support: подключает и настраивает оборудование.

### 4. Визуализация контекста системы — диаграмма С4

[Contexts](https://www.plantuml.com/plantuml/uml/TP6vxjf04CPxdcBZ2YJ0JQfKA0I9I46oE9GI3VPWMzd3sPdbK9HtpopsaeFyksNGz_iEBuZ1Sp1wzAwrfGuLgeQvemzvxk4whrjkmYaG-j9PHilpqfcyqs2ZPaPSwVQKBz_FYdWwRBxa1eZHo-cuZ8eRpxj8Bz2Ji-F66NHNYtwgidLwP_9ZsM3vZHIZwT031u_P98d4_TAMkB9rQ_4XtVKNbKwHyDbA5Qr9WQsKf3stjL184LfodWGtsjr938uVNR0L-Flu2juqJjg9_6jwguspJallRA9-Z9JgHUC1CvIA6GPk3ByzV4e-KsMGeGA6gIAM9j7vIM7KAF_x-s_EFfqYQOlV0nB_DSIZKEW4AMqke0D6vC_KPdNZ8TmpLEowHVtdsY_nDs2X5c25SSb7ZVL-NuXKb2-Jl-eBz6VdJToNGvVrn01QTTu9ZnBe7rrAclo7GzI_eVZFP8TXZBWlzjz-DjYg4hGMqW9j5Op-1G00)

# Задание 2. Проектирование микросервисной архитектуры

В этом задании вам нужно предоставить только диаграммы в модели C4. Мы не просим вас отдельно описывать получившиеся микросервисы и то, как вы определили взаимодействия между компонентами To-Be системы. Если вы правильно подготовите диаграммы C4, они и так это покажут.

**Диаграмма контейнеров (Containers)**

[Containers](https://www.plantuml.com/plantuml/uml/ZLJBJXin5DtdAswp2b8Wcwwwub5G5o1HXeebSXABH9r7DFOqHMsbF4gfbAf8NNNNLls1W40C3y8ls7_KOsS61XEaRfAvr_UUStnzx4KXMIoJm2yzQuSDFsboQadP4IzgjPXr5_RQifNK4y7ZHXHA7ig5HXJKEZuBJS-ya4s_NQ-jF9_VDAat6-krW0d9OwHsLz31sY6F5pe6lxJ9On65bLOKyAYBT9NAh_BlCWBrIqtKbVwcpl5_eiPweCvCJBglKjstuRKUbUTAtZuuWjtLzx8YU2WY0-NP3opcgyjH4ZPPl5_fiZXeHTW3gdRoR_8OyyfpzA54T2UqqkNrfKu7TMkntMwJlCqbg-sdkZ42T4z_XemBtITr2d57f6vdgZw2aY9odJNU0cyjYYqq89Ud6KAASZfBzKEDrPLAWJ_MNrHgECwHkjKzDT5zmr8bn2TWcY2NOZKlV4fCrQu0yHBHTts8x0qQpqYbf8SM6e1WpVFWmQTXiqlNAdNsmyH-sF1u_AxTC7DTCY69QKnTk8O2BWJRurIF8snqUiA_WNKCp84QWuBiRexr237K6nR23tJgeTLouP06KJFn-JthXer5pcif_fX3mbvIWz_B-VG8P0NmdErKJV0nTdYQJB8wiuPvkMnGfou3aMGIMNCVH9MCauNJcbNc6dDVkXglz51_LMDe7JXJ82FhrcxYJ9rc9LWuU7GcOFvKAju5_7Tup6GI5sQqVP-aB6ikoHRtYpVnplZgxmmtv6EQpYoTxGw3cCCyTllMghTD7sc7ruMnWymQ7XKMHk-zNYyy2yEYQyrSRg1WXB6O2q3g69bpFQgI7cHNu59DI1yYpBgUOdISd9KzpBfDUPdZoF_2Sbfc5xasWcUA9dbu0hZg6OZRvhoEWZfn9AD6vC-IFtFueDK7vfIpqLlAldrwZcpg8eDopUUEO_P9JX_rpEzuhh3Oiq_y8iQT1Fu_)

**Диаграмма компонентов (Components)**

[BFF](https://www.plantuml.com/plantuml/uml/ZLBDRjD04BxdAOQSKgcjBvmubOHM78fKDK4SguszeHRshhMxBh80YHPLFHIfpm1Fa1H2J4lSLvXz8sOZEudT7dAn_FtCD_RCx6d3b4dZgFKi57wK1XnEZKdq2yzJxEFk-z2SfiDKS-LBORWmkxwClIHYmjNiQ1D4uT3hFTyvSjJRDuTUpBJXYgYJdemJALnDul9x5C12mTL9LwOYO2hh34UZRMXtcV-1Ym0Ef883HIu2xItur09OHdGKr-QGPLnHmV5-Vm0Bq2Q4F_0U2_mBzYkESOA5lR3NOCy1PuGVY2tiERtzmnpmWPptzZj91TxYs5xWbF1DUwlMZ9_HKrVjzXTeWuRKfi29lQRKtDwuXerSpTLPwFDbSh_4JsHJReupdEEKWXVSBoBk7aKgdaWT6ccovNHAHcMRp6X2UEOaolsosb5dv1P1bQk5h8a1CwpBD2VzLRUcC9q9l_mjKbyw22KcO-kOHrNq-aPV3mP7VVWCx_XGIxe6GrvdNVCqPrSwobLjxcbyOMcfixM2oj88Nms-uNiah4qBVvRtTuS5sAl5-Sqnn-bsTPhVx5N5kNkw9V07Sti9-1l7nC_fl2wfqnxj98sZ_m00)

[Modules Service](https://www.plantuml.com/plantuml/uml/XL7Dhj905Dxp56DNlOdtTkFArHLa1ub1NPEXFKYJTgQP7xGn9efB5Zw3Ro1HGb7a6SwyaMSG6Gj4awR9zvtl9-VClJPS6LiMdGUvI0kR0PiPK-d7IQBuwxjNkPdPYTMWKYaC27ENoZAf2YwyvrQRhCWdIU_HxJDFlHmEaf9h0ugeSK-MbHJUK_dy7WNmN80QTwKL6LTrF9bE7x9eA3DRW6RFGStp5A8RzhR3sCaTmvp-Ui1hKAJk7n0xm8WmViOVkCSjS-_n2wvmxnPkoTm7-eXUkQLROEC-uGwRwAQLgt_tdPAF_TUoARV13Vx4DGKVkAz4VCU6uOx0D_UHo3LkpneKL5BdHfhwJyVeoAZw_njGA-6D7r7kkt30EEE6Txa6CZ_jqYnCkAv5Ubo4fayy38SDmd7_ZOaDb1KeRgo2O7aHoB-CdH4KP-7jPo6DbxJ8jlwgfFK6GND6Xpl-MtUvK91UP8GZUiazYCoMnIy0)

[Sensors service](https://www.plantuml.com/plantuml/uml/ZP1FIiD05CRtESMOLGkssRXoLGtkAeZ5TPac3nkOp8JvKmaYQBTTU0PlO1T2HUqPtjp8cIPaYBWeXC3xtcz-aoyJfQdKfcJHIS4pPd8WIwqhTPuaaZwCxmkzD0kZG6Q2Q-1wd8aogHZb_in8wPmLYoGz6ztuwEvwcfHKQP0kcgUYh0JtPohlJvs05Xpa_58OdbDP3nHm9QIQWLmL6PoIUDO4f4tY8NcC2Eb40rYvjvhI6gIZhmuJEOonc_4Dlt2FdyG-upjkSM_NTaFiYtjSlBKRkyQTVSLltCN3dhVva4xSNd-a-WD__0L-qwgVGjbMtNLpsx2ZgkPPQ7_Xnz0zYcw1_M7wFy0n7kc5FVv_fDUsGq8Qc6Ox0PwRalq2)

**Диаграмма кода (Code)**

[Module](https://www.plantuml.com/plantuml/uml/VP51QyGW48Nl_WgFbcN_G0vbsPRI7dhfxhtOECqAKSFC60Yb_xtMR0WHoMN0b_TUFiSJiKQEhfVlmSGUw2aO46slYHRbHRSSS98_Gif31ppB5y3Hjd2UhjC0YjDe935Qtpqqz-GhQ0Qy6yMlc6it7tDfGk18Ipm936u0J2AcKX_T5s1IRy51a-UdDUaS2R39CvtN-ig_P_GM_pLbE5G1dpaKv3bqqxw3IoPKMz2Acu2lAxkgtAC8xM9_m138hhidFO9osRUqfBenv6qSlgqtv-dDA6jAmhnyKJpdyVXOVQUAbhsxW68VlyoB4tWJNVy7)

# Задание 3. Разработка ER-диаграммы

[ER](https://www.plantuml.com/plantuml/uml/bL11JxD04BtlhvWllPJaQxmJGehQfZL13GKzab6ckf5TcjtP14Bzxm9D5I-eUzXatvjzRzvRMaR3JfNmY4QzLixIAX7_2jfBJS3uLDAyze0qIswWXY20UVf_jbv7tV4W33zd3qOgD4t-Hat_8t1X7LouBtvV6P8l-ipFQY5Eyfabuq4hu9k4B3mVicnxtU6aK9O-F4J9rIPAEa2Zel7xsH0o5Jco3-asNktIABuNxsU7JHzhscAyNJTiyX7vatnS5QxyW_xGSlvhTsuED1NUChApOqGHemytkxlRowdjXUYhX-DniMXXw4WCzu1KBPnoYINfmgdo0m00)

# Задание 4. Создание и документирование API

### 1. Тип API

Для взаимодействия микросервисов используется комбинация:

**REST API (HTTP/JSON)** — для синхронных запросов:

**AsyncAPI (Kafka)** — для асинхронного обмена событиями:

**Обоснование решения:**

- REST API является стандартным и широко используемым подходом для синхронного взаимодействия микросервисов, подходит для синхронных запросов, где требуется немедленный ответ
- Kafka обеспечивает надёжную доставку событий и масштабирование сервисов. Позволяет обрабатывать большой поток телеметрии от тысяч датчиков без блокировки основных сервисов. Поддерживает replay событий при сбоях.

### 2. Документация API

#### REST API (OpenAPI/Swagger)

Документация REST API находится в файле `apps/smart_home/api-docs.yaml`.

#### AsyncAPI (Kafka)

Документация ASYNC API находится в файле `apps/smart_home/async-api.yaml`.

# Задание 5. Работа с docker и docker-compose

Перейдите в apps.

Там находится приложение-монолит для работы с датчиками температуры. В README.md описано как запустить решение.

Вам нужно:

1. сделать простое приложение temperature-api на любом удобном для вас языке программирования, которое при запросе /temperature?location= будет отдавать рандомное значение температуры.

Locations - название комнаты, sensorId - идентификатор названия комнаты

```
	// If no location is provided, use a default based on sensor ID
	if location == "" {
		switch sensorID {
		case "1":
			location = "Living Room"
		case "2":
			location = "Bedroom"
		case "3":
			location = "Kitchen"
		default:
			location = "Unknown"
		}
	}

	// If no sensor ID is provided, generate one based on location
	if sensorID == "" {
		switch location {
		case "Living Room":
			sensorID = "1"
		case "Bedroom":
			sensorID = "2"
		case "Kitchen":
			sensorID = "3"
		default:
			sensorID = "0"
		}
	}
```

2. Приложение следует упаковать в Docker и добавить в docker-compose. Порт по умолчанию должен быть 8081

3. Кроме того для smart_home приложения требуется база данных - добавьте в docker-compose файл настройки для запуска postgres с указанием скрипта инициализации ./smart_home/init.sql

Для проверки можно использовать Postman коллекцию smarthome-api.postman_collection.json и вызвать:

- Create Sensor
- Get All Sensors

Должно при каждом вызове отображаться разное значение температуры

Ревьюер будет проверять точно так же.
