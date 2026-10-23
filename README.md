import tkinter as tk
from tkinter import messagebox


def show_product_details(name, price, desc):
  messagebox.showinfo(
      name, f"التفاصيل:\n{desc}\n\nالسعر: {price}\n\nتم اختيار المنتج بنجاح!"
  )


# إنشاء النافذة الرئيسية لتطبيق المتجر
root = tk.Tk()
root.title("متجر العكادي لأدوات التجميل")
root.geometry("360x640")
root.configure(bg="#fff0f5")

# عنوان المتجر في الواجهة
title_label = tk.Label(
    root,
    text="✨ متجر العكادي للتجميل ✨",
    font=("Arial", 16, "bold"),
    bg="#fff0f5",
    fg="#d81b60",
)
title_label.pack(pady=20)

# قائمة المنتجات
products = [
    (
        "أحمر شفاه مات (Matte Lipstick)",
        "10$",
        "ثابت يدوم طويلاً، ترطيب عالي وملمس مخملي.",
    ),
    (
        "باليت عيون بريق (Eyeshadow Palette)",
        "22$",
        "ألوان جذابة ومتنوعة تناسب جميع المناسبات والسهرات.",
    ),
    (
        "كريم أساس مرطب (Foundation)",
        "18$",
        "تغطية كاملة ومثالية لبشرة صافية ومشرقة طوال اليوم.",
    ),
    (
        "ماسكرة تكثيف الرموش",
        "12$",
        "تكثيف وتطويل فوري للرموش بدون تكتل.",
    ),
]

# عرض المنتجات داخل الواجهة كأزرار
for prod_name, prod_price, prod_desc in products:
  btn = tk.Button(
      root,
      text=f"{prod_name}\nالسعر: {prod_price}",
      font=("Arial", 11),
      bg="#ffffff",
      fg="#333333",
      width=30,
      height=2,
      command=lambda n=prod_name, p=prod_price, d=prod_desc: (
          show_product_details(n, p, d)
      ),
  )
  btn.pack(pady=10)

# تشغيل التطبيق
root.mainloop()

