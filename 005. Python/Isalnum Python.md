#flashcards/Python 
***
***Расшифровка:*** is alphanumeric.
Метод, встроенный в Python, который проверяет, из каких символов состоит строка.
- Проверяет, является ли строка буквенно-цифровой.
- Возвращает `true`, если строка содержит только буквы и цифры, а также в ней нет спецсимволов и пробелов.
***
***Примеры.***
```python
"Python3".isalnum() # true
"67".isalnum()      # true
"Привет".isalnum()  # true

"hi man".isalnum()  # false
"hello!"            # false
"".isalnum()        # false 
```