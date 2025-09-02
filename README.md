# todo_list.py

tasks = []

def show_tasks():
    if not tasks:
        print("📭 هیچ کاری وجود ندارد.")
    else:
        print("\n📝 لیست کارها:")
        for i, task in enumerate(tasks, start=1):
            print(f"{i}. {task}")
    print()

def add_task():
    task = input("➕ یک کار جدید وارد کنید: ")
    tasks.append(task)
    print("✅ کار اضافه شد!\n")

def remove_task():
    show_tasks()
    if tasks:
        num = int(input("❌ شماره کار برای حذف: "))
        if 1 <= num <= len(tasks):
            removed = tasks.pop(num - 1)
            print(f"🗑 کار '{removed}' حذف شد.\n")
        else:
            print("❌ شماره نامعتبر!\n")

def main():
    while True:
        print("=== 📌 مدیریت کارها ===")
        print("1. نمایش کارها")
        print("2. افزودن کار")
        print("3. حذف کار")
        print("4. خروج")
        
        choice = input("انتخاب کنید: ")
        if choice == "1":
            show_tasks()
        elif choice == "2":
            add_task()
        elif choice == "3":
            remove_task()
        elif choice == "4":
            print("👋 خداحافظ!")
            break
        else:
            print("❌ انتخاب نامعتبر!\n")

if __name__ == "__main__":
    main()
