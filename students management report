def student_management_system():
    # Initial dataset (array of student records)
    students = [
        {"name": "Alice Smith", "marks": [88, 92, 85]},
        {"name": "Bob Jones", "marks": [65, 58, 70]},
        {"name": "Charlie Brown", "marks": [45, 40, 48]},
        {"name": "Diana Prince", "marks": [95, 91, 94]}
    ]
    
    while True:
        print("\n==============================")
        print("   STUDENT MANAGEMENT MENU    ")
        print("==============================")
        print("1. View All Student Reports")
        print("2. Add a New Student")
        print("3. View Class Summary Stats")
        print("4. Exit Program")
        
        choice = input("Enter your choice (1-4): ").strip()
        
        if choice == '1':
            if not students:
                print("\n[!] No student records found.")
                continue
                
            print("\n--- STUDENT PERFORMANCE REPORT ---")
            print(f"{'Student Name':<18} | {'Average':<8} | {'Grade':<6} | {'Status'}")
            print("-" * 55)
            
            for student in students:
                name = student["name"]
                marks = student["marks"]
                avg = sum(marks) / len(marks)
                
                if avg >= 85:
                    grade, status = "A", "Distinction"
                elif avg >= 70:
                    grade, status = "B", "Merit"
                elif avg >= 50:
                    grade, status = "C", "Pass"
                else:
                    grade, status = "F", "Fail"
                    
                print(f"{name:<18} | {avg:<8.2f} | {grade:<6} | {status}")
                
        elif choice == '2':
            name = input("\nEnter student's full name: ").strip()
            if not name:
                print("[!] Name cannot be empty.")
                continue
                
            try:
                marks_input = input("Enter marks separated by spaces (e.g., 85 90 78): ")
                marks = [float(mark) for mark in marks_input.split()]
                if not marks:
                    print("[!] Please enter at least one mark.")
                    continue
            except ValueError:
                print("[!] Invalid input. Please enter numbers only.")
                continue
                
            students.append({"name": name, "marks": marks})
            print(f"[Success] Added {name} to the database!")
            
        elif choice == '3':
            if not students:
                print("\n[!] No student records to analyze.")
                continue
                
            total_class_avg = 0
            top_student = ""
            highest_avg = -1
            
            for student in students:
                avg = sum(student["marks"]) / len(student["marks"])
                total_class_avg += avg
                if avg > highest_avg:
                    highest_avg = avg
                    top_student = student["name"]
                    
            class_average = total_class_avg / len(students)
            
            print("\n--- CLASS PERFORMANCE SUMMARY ---")
            print(f"Total Students  : {len(students)}")
            print(f"Class Average   : {class_average:.2f}")
            print(f"Top Performer   : {top_student} ({highest_avg:.2f})")
            
        elif choice == '4':
            print("\nExiting Student Management System. Goodbye!")
            break
        else:
            print("\n[!] Invalid choice. Please select a number between 1 and 4.")

if __name__ == "__main__":
    student_management_system()