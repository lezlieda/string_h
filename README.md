# string_h
Implementation of some functions from the string.h library with additions.

### string.h Типы

| № | Переменная |
| ------ | ------ |
| 1 | size_t |
	
### string.h Макросы

| № | Макрос |
| ------ | ------ |
| 1 | NULL |

### string.h Функции

| № | Функция |
| ------ | ------ |
| 1 | void *memchr(const void *str, int c, size_t n) |
| 2 | int memcmp(const void *str1, const void *str2, size_t n) |
| 3 | void *memcpy(void *dest, const void *src, size_t n) | 
| 4 | void *memmove(void *dest, const void *src, size_t n) | 
| 5 | void *memset(void *str, int c, size_t n) |
| 6 | char *strcat(char *dest, const char *src) | 
| 7 | char *strncat(char *dest, const char *src, size_t n) |
| 8	| char *strchr(const char *str, int c) | 
| 9 | int strcmp(const char *str1, const char *str2) | 
| 10 | int strncmp(const char *str1, const char *str2, size_t n) | 
| 11 | char *strcpy(char *dest, const char *src) | 
| 12 | char *strncpy(char *dest, const char *src, size_t n) | 
| 13 | size_t strcspn(const char *str1, const char *str2) | 
| 14 | char *strerror(int errnum) | 
| 15 | size_t strlen(const char *str) | 
| 16 | char *strpbrk(const char *str1, const char *str2) | 
| 17 | char *strrchr(const char *str, int c) | 
| 18 | size_t strspn(const char *str1, const char *str2) | 
| 19 | char *strstr(const char *haystack, const char *needle) | 
| 20 | char *strtok(char *str, const char *delim) | 

### stdio.h Функции

| № | Функция |
| ------ | ------ |
| 1 | int sscanf(const char *str, const char *format, ...) |

Для функции **sprintf** поддерживается частичное форматирование:
  - Спецификаторы: c, d, i, f, s, u, p, o, x, X, n, %
  - Флаги: -, +, (пробел), #, 0
  - Ширина: (число), *
  - Точность: .(число), *
  - Длина: h, l

### Специальные функции обработки строк (вдохновленные классом String в языке C#)

| № | Функция | Описание |
| ------ | ------ | ------ |
| 1 | void *to_upper(const char *str) | Возвращает копию строки (str), преобразованной в верхний регистр. В случае какой-либо ошибки следует вернуть значение NULL |
| 2 | void *to_lower(const char *str) | Возвращает копию строки (str), преобразованной в нижний регистр. В случае какой-либо ошибки следует вернуть значение NULL |
| 3 | void *insert(const char *src, const char *str, size_t start_index) | Возвращает новую строку, в которой указанная строка (str) вставлена в указанную позицию (start_index) в данной строке (src). В случае какой-либо ошибки следует вернуть значение NULL |
| 4 | void *trim(const char *src, const char *trim_chars) | Возвращает новую строку, в которой удаляются все начальные и конечные вхождения набора заданных символов (trim_chars) из данной строки (src). В случае какой-либо ошибки следует вернуть значение NULL |


К сожалению, для функции sprintf не удалось реализовать спецификаторы **g**, **G**, **e**, **E** по причине нехватки времени плюс кривой, как мне казалось, работы спецификатора **f** - точность всё время уплывала от меня из одного места в другое, так что закостылил компромиссный вариант. Автотест же такую точность схавал ~~и попросил добавки~~ и, вероятно, можно было делать проще и без костылей.

Проект делался "под мак", соответственно на линухе не все тесты проходят успешно, а конкретно по разному работают функции memcmp и sprintf.