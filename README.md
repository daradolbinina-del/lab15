# Домашнее задание к работе 15
## Условие задачи
В двумерном массиве хранится информация о зарплате 18 человек за каждый месяц года (за январь — в первом столбце, за февраль — во втором и т. д.). Определить общую зарплату, выплаченную в июне.
## 1. Алгоритм и блок-схема
## Алгоритм
1. Начало

2. Инициализация генератора случайных чисел

3. Объявление двумерного массива salary[18][12] для хранения зарплат

4. Заполнение массива случайными значениями зарплат (от 20000 до 100000)

5. Вывод таблицы зарплат всех сотрудников за все месяцы

6. Вычисление общей зарплаты, выплаченной в июне (6-й месяц, индекс 5)

7. Вывод зарплаты каждого сотрудника за июнь

8. Вывод общей суммы зарплат за июнь
9. конец

   
### Блок-схема
<img width="286" height="937" alt="image" src="https://github.com/user-attachments/assets/b170cda8-402d-4415-b452-d4ca239c0adb" />





## 2. Реализация программы

```
#define _CRT_SECURE_NO_WARNINGS
#define _USE_MATH_DEFINES
#include <locale.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h> 
#include <conio.h>
#include <math.h>
#define N 7
#include <time.h>

#define PEOPLE 18
#define MONTHS 12

int main() {
    setlocale(LC_ALL, "RUS");
    int salary[PEOPLE][MONTHS];
    int i, j;

    srand(time(NULL));

    printf("Зарплаты 18 человек за 12 месяцев:\n");
    printf("Человек  \\  Месяц: ");
    for (j = 0; j < MONTHS; j++) {
        printf("   %5d ", j + 1);
    }
    printf("\n");

    for (i = 0; i < PEOPLE; i++) {
        printf("Человек %2d: ", i + 1);
        for (j = 0; j < MONTHS; j++) {
            salary[i][j] = 20000 + rand() % 80001; 
            printf("  %5d  ", salary[i][j]);
        }
        printf("\n");
    }

   
    int total_june = 0;
    for (i = 0; i < PEOPLE; i++) {
        total_june += salary[i][5]; 
    }

    printf("\nОбщая зарплата, выплаченная в июне: %d\n", total_june);

    printf("\nЗарплата каждого человека за июнь:\n");
    for (i = 0; i < PEOPLE; i++) {
        printf("Человек %2d: %6d\n", i + 1, salary[i][5]);
    }

    return 0;
}
```


## 3. Результаты работы программы
<img width="1452" height="1121" alt="image" src="https://github.com/user-attachments/assets/e3dc34dd-5b26-435b-a935-e7e2cf7b443a" />



