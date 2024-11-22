# Проект e-commerce

# Описание проекта
В проекте проанализированы совершенные покупки, исследованы основные показатели, которые были предложены продакт-менеджером. Выявлены среднее число покупок в неделю и по месяцам, изучены недоставленные заказы. Для качественной оценки аудитории проведены когортный анализ и RFM-сегментация.

# Входные данные

В качестве входных данных csv-файлы:

* olist_customers_datase.csv (https://disk.yandex.ru/d/QXrVDUoQvFhIcg) — таблица с уникальными идентификаторами пользователей (customer_id — позаказный идентификатор пользователя, customer_unique_id —  уникальный идентификатор пользователя  (аналог номера паспорта), customer_zip_code_prefix —  почтовый индекс пользователя, customer_city —  город доставки пользователя, customer_state —  штат доставки пользователя).
* olist_orders_dataset.csv (https://disk.yandex.ru/d/0zWmh1bYP6REbw) —  таблица заказов (order_id —  уникальный идентификатор заказа (номер чека), customer_id —  позаказный идентификатор пользователя, order_status —  статус заказа, order_purchase_timestamp —  время создания заказа, order_approved_at —  время подтверждения оплаты заказа, order_delivered_carrier_date —  время передачи заказа в логистическую службу, order_delivered_customer_date —  время доставки заказа, order_estimated_delivery_date —  обещанная дата доставки). Уникальные статусы заказов: created —  создан, approved —  подтверждён, invoiced —  выставлен счёт, processing —  в процессе сборки заказа, shipped —  отгружен со склада, delivered —  доставлен пользователю, unavailable —  недоступен, canceled —  отменён.
* olist_order_items_dataset.csv (https://disk.yandex.ru/d/xCsQ0FiC-Ue4Lg) —  товарные позиции, входящие в заказы (order_id —  уникальный идентификатор заказа (номер чека), order_item_id —  идентификатор товара внутри одного заказа, product_id —  ид товара (аналог штрих кода), seller_id — ид производителя товара, shipping_limit_date —  максимальная дата доставки продавцом для передачи заказа партнеру по логистике, price —  цена за единицу товара, freight_value —  вес товара).

# Анализ данных
* Исследование файлов и обьединение данных.
* Нахождение количества пользователей, которые сделали только 1 покупку. Покупка считается совершенной, если заказ имеет статут "delivered".
* Определение числа заказов в месяц в среднем, которые не доставлены по разным причинам (статусы "unavailable" (недоступен) и "canceled" (отменён)).
* Нахождение дня недели, в который товар чаще всего покупается.
* Определение среднего числа покупок в неделю (по месяцам) у каждого из пользователей.
* Выполнен когортный анализ пользователей, выявлены когорты с наивысшим retention в период с января по декабрь.
* Проведена RFM-сегментация пользователей, чтобы качественно оценить аудиторию. В кластеризации выбраны следующие метрики: recency (R) - время от последней покупки пользователя до текущей даты, frequency (F) - суммарное количество покупок у пользователя за всё время, monetary (M) - сумма покупок за всё время. Для каждого RFM-сегмента построены границы метрик recency, frequency и monetary для интерпретации этих кластеров.

#  Выводы
В ходе работы проведен анализ покупательского поведения клиентов. Когортный анализ и RFM-сегментация пользователей могут помочь бизнесу с проведением продуктовых и маркетинговых активностей. Следует сказать, что весьма низкий процент пользователей, которые совершают повторные покупки. Необходима работа над поддержанием спроса и формированием лояльности клиентов.

# Библиотеки и технологии
pandas, numpy, seaborn, matplotlib.

