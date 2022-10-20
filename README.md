# Домашнее задание к занятию "6.2. SQL"



## Задача 1



```
docker run --rm --name db_first -e POSTGRES_PASSWORD=12345 -d -p 5434:5432 -v db_main:/var/lib/postgresql/data -v db_bckp:/var/lib/postgresql  postgres:12
```

## Задача 2



![2-1](https://user-images.githubusercontent.com/106814458/196817244-947e2f2e-310a-42bf-8911-49461c155243.jpg)


описание таблиц (describe)


![2-3](https://user-images.githubusercontent.com/106814458/197016662-f348c8ee-d1e6-4386-8f23-c0117673e705.jpg)




```
select * from information_schema.table_privileges tp where grantee like 'test%'
```
![image](https://user-images.githubusercontent.com/106814458/196817398-a677cc4e-4878-4c64-a39f-6f12507b0bad.png)




## Задача 3




![2-4](https://user-images.githubusercontent.com/106814458/197019533-9b85455b-8e99-49d3-bcf8-222626f1f268.jpg)



## Задача 4



![2-5](https://user-images.githubusercontent.com/106814458/197019595-099a88ac-2580-4e23-a87f-09301a111e06.jpg)


## Задача 5


![2-6](https://user-images.githubusercontent.com/106814458/197019623-b48c2105-c79e-473e-895d-04d19ffdffe1.jpg)

```
Первое значение - приблизительная стоимость запуска(время прежде чем начнется вывод данных

Второе - приблизительная общая стоимость (вычисляется в предположении , что узел плана 
выполняется до конца т.е. возвращает все доступные строки)

Третье - ожидаемое число строк (также предполагается , что узел выполняется до конца)

Четвертое - Ожидаемый средний размер строк
```
## Задача 6


```
C помощью команды docker exec -ti db_first bash  провалился в "основную БД" 
сделал бекап по команде pg_dump -U postgres test_db -f /var/lib/postgresql/data/bd_bckp.sql

Далее в новом контейнере :
root@08b220910fcc:/# psql -U postgres -d test_db -f /var/lib/postgresql/bd_bckp.sql



```




