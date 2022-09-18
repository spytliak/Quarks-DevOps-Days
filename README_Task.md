## Quarks DevOps Days 

### Monitoring Home Work

#### Tasks description:

1 – Grafana  
Побудувати графік на базі метрики probe_http_duration_seconds.  
На цьому графіку повинна бути зображена різниця поточних значень phase і значень котрі були вчора в той же час.  

Візуалізація:  
у legend графіку записати labels у форматі: phase – target, значення вивести на графіку справа, таблицею.  
Увімкнути stack series значень на графіку.  

2 – Prometheus  
Створити Alert  

Умова:  
якщо середнє значення метрики probe_duration_seconds протягом однієї хвилини понад 2 секунди.  

3 – Blackbox exporter  
Завдання на конфігурацію:  
Вважати результат probe неуспішним, якщо на сайті, який ми хочемо моніторити через модуль http_2xx вимкнений  ssl  