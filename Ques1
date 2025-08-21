import pandas as pd
import numpy as np

# إنشاء جدول البيانات (DataFrame)
mydata = {
    'Transaction_ID': [1001, 1002, 1003, 1004, 1005, 1006],
    'Customer_Name': ['Ahmed Ali', 'Sara Omar', 'Ali Saleh', 'Nada Hassan', 'Omar Khalid', 'Ahmed Ali'],
    'Age': [28, np.nan, 35, 42, np.nan, 28],
    'Email': ['ahmed@mail.com', 'sara@mail.com', np.nan, 'nada@mail.com', 'omar@mail.com', 'ahmed@mail.com'],
    'Join_Date': ['2025-01-10', '2025-02-15', '2025-03-20', '2025-05-05', '2025-01-10', '2025-01-10'], # Corrected dates based on common patterns
    'Total_Purchase': [250, 300, 150, 400, np.nan, 250]
}
df = pd.DataFrame(mydata)

print("--- الجدول الأصلي ---")
print(df)
print("\n" + "="*30 + "\n")

# --- الجزء الأول: أوامر Pandas ---

print("--- 1. تحويل عمود Join_Date إلى تاريخ ---")
df['Join_Date'] = pd.to_datetime(df['Join_Date'])
print(df.dtypes)
print("\n")

print("--- 2. تحديد الصفوف التي فيها أكثر من قيمة فارغة ---")
rows = df[df.isnull().sum(axis=1) > 1]
print(rows)
print("\n")

print("--- 3. معرفة نوع البيانات وعدد الصفوف والأعمدة ---")
df.info()
print("\n")

print("--- 4. التحقق من عدد القيم الفارغة في كل عمود ---")
null_valuesincolumn = df.isnull().sum()
print(null_valuesincolumn)
print("\n")

print(" تحديد الصفوف التي العمر فيها > من 30 سنة")
smallAge = df[df['Age'] > 30]
print(smallAge)
print("\n")

print(" معرفة كم صف يتبقى بعد حذف الصفوف التي تحتوي على أي قيم فارغة ")
rowsdropnulls = len(df.dropna())
print(f"عدد الصفوف المتبقية بعد حذف القيم الفارغة: {rowsdropnulls}")
print("\n")

print(" استبدال القيم الفارغة في عمود Age بالمتوسط")
mean_age = df['Age'].mean()
df['Age'].fillna(mean_age, inplace=True)
print("القيم الفارغة في عمود Age بعد استبدالها بالمتوسط:")
print(df)
print("\n")

print("استبدال القيم الفارغة في عمود Total_Purchase بالرقم 0")
df['Total_Purchase'].fillna(0, inplace=True)
print("القيم الفارغة في عمود Total_Purchase بعد استبدالها بالصفر:")
print(df)
print("\n")

print(" معرفة الصفوف المتكررة قبل حذفها")
duplicated_rows = df[df.duplicated(keep=False)]
print(duplicated_rows)
print("\n")

print(" إزالة الصفوف المتكررة")
df.drop_duplicates(inplace=True)
print("الجدول بعد إزالة الصفوف المتكررة:")
print(df)
