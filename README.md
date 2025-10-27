import re

# а) створення файлу TF2_1 із символьних рядків різної довжини
try:
    with open("TF2_1.txt", "w", encoding="utf-8") as f1:
        f1.write("Сьогодні 27 жовтня 2025 року.\n")
        f1.write("Мій номер залікової книжки 1006392.\n")
        f1.write("У групі навчається 7 студентів.\n")
        f1.write("Температура повітря +10 градусів.\n")
        f1.write("Код доступу: 987654321.\n")
    print("Файл TF2_1.txt успішно створено.")
except OSError as e:
    print(f"Помилка створення файлу TF2_1.txt: {e}")

# б) зчитування файлу TF2_1, пошук усіх числових послідовностей довжиною > 2
try:
    with open("TF2_1.txt", "r", encoding="utf-8") as f1:
        text = f1.read()
    # Знаходимо всі числа довші за 2 цифри
    numbers = re.findall(r"\d{3,}", text)
except FileNotFoundError:
    print("Помилка: файл TF2_1.txt не знайдено!")
    numbers = []
except OSError as e:
    print(f"Помилка при читанні TF2_1.txt: {e}")
    numbers = []

# в) Запис знайдених чисел у TF2_2.txt
try:
    with open("TF2_2.txt", "w", encoding="utf-8") as f2:
        f2.write(" ".join(numbers))
    print("Файл TF2_2.txt створено успішно.")
except OSError as e:
    print(f"Помилка запису у файл TF2_2.txt: {e}")

# г) Читання вмісту TF2_2.txt і виведення результату
try:
    with open("TF2_2.txt", "r", encoding="utf-8") as f2:
        result = f2.read()
    print("\nПослідовності цифр (довжиною > 2), знайдені у файлі TF2_1:")
    print(result)
except FileNotFoundError:
    print("Помилка: файл TF2_2.txt не знайдено!")
except OSError as e:
    print(f"Помилка при читанні TF2_2.txt: {e}")
