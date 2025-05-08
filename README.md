# Lab_12
## 📌 Опис
Програма створена з використанням модуля `tkinter`. Дозволяє взаємодіяти з користувачем через графічний інтерфейс.

## 🧩 Використані віджети
- `Label` — для відображення тексту
- `Button1` - кнопка 1
- `Button2` - кнопка 2
- `Labelpack1` - поле введення 1
- `Labelpack2` - поле введення 2
- `Labelpack3` - поле введення 3
- `Labelpack4` - поле введення 4
- `Labelpack5` - поле введення 5
- `Checkbutton1` - кнопка перевірки 1
- `Checkbutton2` - кнопка перевірки 2
- `Radiobutton1` - перемикач 1
- `Radiobutton2` - перемикач 2
- `Radiobutton3` - перемикач 3
- `Radiobutton4` - перемикач 4

## 🖱 Події
- `command=` — обробка натискання кнопки
- `get()` — зчитування значення з `Entry`

## 📐 Геометрія


from tkinter import *
from tkinter import messagebox

def show():
    global photo
    photo = PhotoImage(file='11.png')
    label5.configure(image=photo)

def inf():
    s = edit4.get()
    if s == "111":
        messagebox.showinfo("Про спеціальність", s + "\nСпеціальність 111 Математика\nОсвітня програма Комп'ютерна математика")
    elif s == "СОМ" or s == "014":
        messagebox.showinfo("Про спеціальність", s + "\nСпеціальність 014 Середня освіта\nОсвітня програма Середня освіта. Математика, інформатика")
    else:
        messagebox.showinfo("Про спеціальність", s + "\nТакої спеціальності на факультеті немає")

root = Tk()
root.geometry('400x550+500+100')
root.title("Анкета")

# Прізвище
Label(root, text="Прізвище:", justify=CENTER).grid(row=0, column=0, sticky=E, padx=5, pady=5)
edit1 = Entry(root, width=25)
edit1.grid(row=0, column=1, padx=5, pady=5)

# Ім'я
Label(root, text="Ім'я:", justify=CENTER).grid(row=1, column=0, sticky=E, padx=5, pady=5)
entry2 = Entry(root, width=25)
entry2.grid(row=1, column=1, padx=5, pady=5)

# По батькові
Label(root, text="По батькові:", justify=CENTER).grid(row=2, column=0, sticky=E, padx=5, pady=5)
entry3 = Entry(root, width=25)
entry3.grid(row=2, column=1, padx=5, pady=5)

# Стать
checkbutton1 = Checkbutton(root, text='ч')
checkbutton1.grid(row=3, column=0, padx=5, pady=5)
checkbutton2 = Checkbutton(root, text='ж')
checkbutton2.grid(row=3, column=1, padx=5, pady=5)

# Вибір курсу
Label(root, text="Виберіть курс:").grid(row=4, column=0, padx=5, pady=5)
result1 = IntVar()
result1.set(1)
Radiobutton(root, text=1, variable=result1, value=1).grid(row=5, column=0, padx=5, pady=2)
Radiobutton(root, text=2, variable=result1, value=2).grid(row=5, column=1, padx=5, pady=2)
Radiobutton(root, text=3, variable=result1, value=3).grid(row=6, column=0, padx=5, pady=2)
Radiobutton(root, text=4, variable=result1, value=4).grid(row=6, column=1, padx=5, pady=2)

# Спеціальність
label5 = Label(root, text="Спеціальність")
label5.grid(row=7, column=0, padx=5, pady=5)
edit4 = Entry(root, width=25)
edit4.grid(row=7, column=1, padx=5, pady=5)

# Кнопки
Button(root, text="Про спеціальність", width=20, command=inf).grid(row=8, column=0, columnspan=2, pady=10)
Button(root, text="Фото", width=20, command=show).grid(row=9, column=0, columnspan=2, pady=10)

root.mainloop()
