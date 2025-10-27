import re

# а) створення файлу TF2_1 із символьних рядків різної довжини
with open("TF2_1.txt", "w", encoding="utf-8") as f1:
    f1.write("Сьогодні 27 жовтня 2025 року.\n")
    f1.write("Мій номер залікової книжки 1006392.\n")
    f1.write("У групі навчається 7 студентів.\n")
    f1.write("Температура повітря +10 градусів.\n")
    f1.write("Код доступу: 987654321.\n")

# б) зчитування файлу TF2_1, пошук усіх числових послідовностей довжиною > 2
with open("TF2_1.txt", "r", encoding="utf-8") as f1:
    text = f1.read()

# Знаходимо всі числа довші за 2 цифри
numbers = re.findall(r"\d{3,}", text)

# Записуємо знайдені числа у TF2_2 через пробіл
with open("TF2_2.txt", "w", encoding="utf-8") as f2:
    f2.write(" ".join(numbers))

# в) Читаємо вміст TF2_2 і виводимо його на екран
with open("TF2_2.txt", "r", encoding="utf-8") as f2:
    result = f2.read()

print("Послідовності цифр (довжиною > 2), знайдені у файлі TF2_1:")
print(result)
