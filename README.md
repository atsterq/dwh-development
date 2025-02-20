# Задача
Реализовать локальное хранилище для информации по аналитическим и балансовым счетам. 
Информация по счетам обновляется 4 раза в день, забирается из накопленного источника (внешняя 
БД).  
Фактические данные – проводки по счетам.  
Форматы данных: табличные.  

# Выбор типа хранилища данных
Для данной задачи подойдет классический Data Warehouse:
- dwh идеально подходит для отчетности (проводки по счетам);
- данные в структурированном формате в виде таблиц;
- загрузка 4 раза в день;  

Слои данных:
- Staging - для первичной загрузки данных из накопленного источника, "как есть";
- Storage - для хранения и обработанных данных в более структурированном виде;
- Presentation - для построения бизнес-витрин;

Данные слои позволят разделить загрузку данных, обработку и представление в виде витрин. Каждый слой имеет свою цель, что позволяет оптимизировать каждый этап. В случаем необходимости, можно будет масштабировать, что при меньшем количестве слоев было бы сложнее.