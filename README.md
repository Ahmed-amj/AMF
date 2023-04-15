import tkinter as tk
from tkinter import PhotoImage
import tkinter.messagebox as messagebox
from tkinter import messagebox as msgbox
import csv
import re
from tkinter import ttk


def main_window_function():
    def student_button_clicked():
        def check_login():
            username = login_entry.get()
            password = password_entry.get()
            with open("studentlogin.csv", "r") as login_file:
                csv_reader = csv.reader(login_file)
                for row in csv_reader:
                    if row[0] == username and row[1] == password:
                        print("Access granted.")
                        login_window.destroy()
                        student_screen()
                        return
            messagebox.showerror("Error", "Incorrect username or password")

        window.destroy()
        login_window = tk.Tk()
        login_window.geometry("300x300")
        login_window.title("Student Login")

        login_label = tk.Label(login_window, text="Username:", font=("Arial", 12, "bold"))
        login_label.grid(row=0, column=0, padx=5, pady=10)
        login_entry = tk.Entry(login_window, width=24, font=("Arial", 14), fg="blue")
        login_entry.grid(row=0, column=1, padx=0, pady=10)

        password_label = tk.Label(login_window, text="Password:",font=("Arial", 12, "bold"))
        password_label.grid(row=1, column=0, padx=5, pady=10)
        password_entry = tk.Entry(login_window, width=24, show="*", font=("Arial", 14), fg="blue")
        password_entry.grid(row=1, column=1, padx=0, pady=10)

        back_button = tk.Button(login_window, text="Back", command=lambda: [login_window.destroy(), main_window_function()], font=("Arial", 12, "bold"))
        back_button.config(width=7, height=3)
        back_button.grid(row=2, column=0, padx=10, pady=10)

        login_button = tk.Button(login_window, text="Login", command=check_login, font=("Arial", 12, "bold"))
        login_button.config(width=7, height=3)
        login_button.grid(row=2, column=1, padx=10, pady=10)

        background_image = PhotoImage(file="SunmarkeLogo.png")
        background_label = tk.Label(login_window, image=background_image)
        background_label.place(x=0, y=80, relwidth=1, relheight=1)
        background_label.lower()

        login_window.mainloop()

    def teacher_button_clicked():
        def check_login():
            username = login_entry.get()
            password = password_entry.get()
            with open("teacherlogin.csv", "r") as login_file:
                csv_reader = csv.reader(login_file)
                for row in csv_reader:
                    if row[0] == username and row[1] == password:
                        print("Access granted.")
                        login_window.destroy()
                        teacher_screen()
                        return
            messagebox.showerror("Error", "Incorrect username or password")

        window.destroy()
        login_window = tk.Tk()
        login_window.geometry("300x300")
        login_window.title("Teacher Login")

        login_label = tk.Label(login_window, text="Username:", font=("Arial", 12, "bold"))
        login_label.grid(row=0, column=0, padx=5, pady=10)
        login_entry = tk.Entry(login_window, width=24, font=("Arial", 14), fg="blue")
        login_entry.grid(row=0, column=1, padx=0, pady=10)

        password_label = tk.Label(login_window, text="Password:",font=("Arial", 12, "bold"))
        password_label.grid(row=1, column=0, padx=5, pady=10)
        password_entry = tk.Entry(login_window, width=24, show="*", font=("Arial", 14), fg="blue")
        password_entry.grid(row=1, column=1, padx=0, pady=10)

        back_button = tk.Button(login_window, text="Back", command=lambda: [login_window.destroy(), main_window_function()], font=("Arial", 12, "bold"))
        back_button.config(width=7, height=3)
        back_button.grid(row=2, column=0, padx=10, pady=10)

        login_button = tk.Button(login_window, text="Login", command=check_login, font=("Arial", 12, "bold"))
        login_button.config(width=7, height=3)
        login_button.grid(row=2, column=1, padx=10, pady=10)

        background_image = PhotoImage(file="SunmarkeLogo.png")
        background_label = tk.Label(login_window, image=background_image)
        background_label.place(x=0, y=80, relwidth=1, relheight=1)
        background_label.lower()

        login_window.mainloop()

    def admin_button_clicked():
        def check_login():
            username = login_entry.get()
            password = password_entry.get()
            with open("adminlogin.csv", "r") as login_file:
                csv_reader = csv.reader(login_file)
                for row in csv_reader:
                    if row[0] == username and row[1] == password:
                        print("Access granted.")
                        login_window.destroy()
                        admin_screen()
                        return
            messagebox.showerror("Error", "Incorrect username or password")

        window.destroy()
        login_window = tk.Tk()
        login_window.geometry("300x300")
        login_window.title("Admin Login")

        login_label = tk.Label(login_window, text="Username:", font=("Arial", 12, "bold"))
        login_label.grid(row=0, column=0, padx=5, pady=10)
        login_entry = tk.Entry(login_window, width=24, font=("Arial", 14), fg="blue")
        login_entry.grid(row=0, column=1, padx=0, pady=10)

        password_label = tk.Label(login_window, text="Password:",font=("Arial", 12, "bold"))
        password_label.grid(row=1, column=0, padx=5, pady=10)
        password_entry = tk.Entry(login_window, width=24, show="*", font=("Arial", 14), fg="blue")
        password_entry.grid(row=1, column=1, padx=0, pady=10)

        back_button = tk.Button(login_window, text="Back", command=lambda: [login_window.destroy(), main_window_function()], font=("Arial", 12, "bold"))
        back_button.config(width=7, height=3)
        back_button.grid(row=2, column=0, padx=10, pady=10)

        login_button = tk.Button(login_window, text="Login", command=check_login, font=("Arial", 12, "bold"))
        login_button.config(width=7, height=3)
        login_button.grid(row=2, column=1, padx=10, pady=10)

        background_image = PhotoImage(file="SunmarkeLogo.png")
        background_label = tk.Label(login_window, image=background_image)
        background_label.place(x=0, y=80, relwidth=1, relheight=1)
        background_label.lower()

        login_window.mainloop()

    def student_screen():
        student_window = tk.Tk()
        student_window.geometry("300x300")
        student_window.title("Student Screen")
        student_window.mainloop()


    def admin_screen():
        admin_window = tk.Tk()
        admin_window.geometry("300x300")
        admin_window.title("admin Screen")
        admin_window.mainloop()

    def teacher_screen():
        def display_student_info():
            with open("studentscores.csv") as file:
                reader = csv.reader(file)
                # headers = next(reader)
                students = list(reader)

            def on_select(event):
                selected = listbox.get(listbox.curselection())
                for student in students:
                    if selected == student[0]:
                        full_name.config(text=student[0], font=("Arial", 12, "bold"))
                        score1.config(text=student[1], font=("Arial", 12, "bold"))
                        score2.config(text=student[2], font=("Arial", 12, "bold"))
                        score3.config(text=student[3], font=("Arial", 12, "bold"))
                        score4.config(text=student[4], font=("Arial", 12, "bold"))
                        score5.config(text=student[5], font=("Arial", 12, "bold"))
                        score6.config(text=student[6], font=("Arial", 12, "bold"))

            teacher_window = tk.Tk()
            teacher_window.geometry("400x900")
            teacher_window.title("Teacher Screen")

            listbox = tk.Listbox(teacher_window, width=50, height=15)
            listbox.pack()

            for student in students:
                listbox.insert(tk.END, student[0])
            listbox.bind("<<ListboxSelect>>", on_select)
            full_name = tk.Label(teacher_window, text="", font=("Arial", 12, "bold"), fg = "blue")
            full_name.pack()
            tk.Label(teacher_window, text="Score 1:", font=("Arial", 10, "bold")).pack()
            score1 = tk.Label(teacher_window, text="", font=("Arial", 12, "bold"), fg = "blue")
            score1.pack()
            tk.Label(teacher_window, text="Score 2:", font=("Arial", 10, "bold")).pack()
            score2 = tk.Label(teacher_window, text="", font=("Arial", 12, "bold"), fg = "blue")
            score2.pack()
            tk.Label(teacher_window, text="Score 3:", font=("Arial", 10, "bold")).pack()
            score3 = tk.Label(teacher_window, text="", font=("Arial", 12, "bold"), fg = "blue")
            score3.pack()
            tk.Label(teacher_window, text="Score 4:", font=("Arial", 10, "bold")).pack()
            score4 = tk.Label(teacher_window, text="", font=("Arial", 12, "bold"), fg = "blue")
            score4.pack()
            tk.Label(teacher_window, text="Score 5:", font=("Arial", 10, "bold")).pack()
            score5 = tk.Label(teacher_window, text="", font=("Arial", 12, "bold"), fg = "blue")
            score5.pack()
            tk.Label(teacher_window, text="Score 6:", font=("Arial", 10, "bold")).pack()
            score6 = tk.Label(teacher_window, text="", font=("Arial", 12, "bold"), fg = "blue")
            score6.pack()

            def add_scores():
                teacher_window.withdraw()
                add_scores_window = tk.Tk()
                add_scores_window.geometry("330x400")
                add_scores_window.title("Add Scores")

                tk.Label(add_scores_window, text="Full Name:", font=("Arial", 12, "bold"), pady=10).grid(row=0, column=0)
                full_name_entry = tk.Entry(add_scores_window, font=("Arial", 14), fg="blue")
                full_name_entry.grid(row=0, column=1)
                tk.Label(add_scores_window, text="Score 1:", font=("Arial", 12, "bold"), pady=10).grid(row=1, column=0)
                score1_entry = tk.Entry(add_scores_window, font=("Arial", 14), fg="blue")
                score1_entry.grid(row=1, column=1)
                tk.Label(add_scores_window, text="Score 2:", font=("Arial", 12, "bold"), pady=10).grid(row=2, column=0)
                score2_entry = tk.Entry(add_scores_window, font=("Arial", 14), fg="blue")
                score2_entry.grid(row=2, column=1)
                tk.Label(add_scores_window, text="Score 3:", font=("Arial", 12, "bold"), pady=10).grid(row=3, column=0)
                score3_entry = tk.Entry(add_scores_window, font=("Arial", 14), fg="blue")
                score3_entry.grid(row=3, column=1)
                tk.Label(add_scores_window, text="Score 4:", font=("Arial", 12, "bold"), pady=10).grid(row=4, column=0)
                score4_entry = tk.Entry(add_scores_window, font=("Arial", 14), fg="blue")
                score4_entry.grid(row=4, column=1)
                tk.Label(add_scores_window, text="Score 5:", font=("Arial", 12, "bold"), pady=10).grid(row=5, column=0)
                score5_entry = tk.Entry(add_scores_window, font=("Arial", 14), fg="blue")
                score5_entry.grid(row=5, column=1)
                tk.Label(add_scores_window, text="Score 6:", font=("Arial", 12, "bold"), pady=10).grid(row=6, column=0)
                score6_entry = tk.Entry(add_scores_window, font=("Arial", 14), fg="blue")
                score6_entry.grid(row=6, column=1)

                def save_to_csv():
                    full_name = full_name_entry.get()
                    match = re.match("^[A-Za-z\s]+$", full_name)
                    if match:
                        score1 = score1_entry.get()
                        score2 = score2_entry.get()
                        score3 = score3_entry.get()
                        score4 = score4_entry.get()
                        score5 = score5_entry.get()
                        score6 = score6_entry.get()

                        if all(map(lambda x: x.isnumeric() and 0 <= int(x) <= 100,
                                   [score1, score2, score3, score4, score5, score6])):
                            data = [[full_name, score1, score2, score3, score4, score5, score6]]
                            with open("studentscores.csv", "a", newline="") as file:
                                writer = csv.writer(file)
                                writer.writerows(data)

                            full_name_entry.delete(0, tk.END)
                            score1_entry.delete(0, tk.END)
                            score2_entry.delete(0, tk.END)
                            score3_entry.delete(0, tk.END)
                            score4_entry.delete(0, tk.END)
                            score5_entry.delete(0, tk.END)
                            score6_entry.delete(0, tk.END)
                        else:
                            tk.messagebox.showerror("Error",
                                                    "Invalid Scores, Please enter only numbers between 0 and 100.")
                    else:
                        tk.messagebox.showerror("Error", "Invalid Name, Please enter only Alphabets and spaces")

                def go_back():
                    add_scores_window.destroy()
                    display_student_info()

                back_button = tk.Button(add_scores_window, text="Back", command=go_back, font=("Arial", 12, "bold"))
                back_button.config(width=7, height=3)
                back_button.grid(row=7, column=0, padx=0, pady=10)

                save_button = tk.Button(add_scores_window, text="Save", command=save_to_csv, font=("Arial", 12, "bold"))
                save_button.config(width=7, height=3)
                save_button.grid(row=7, column=1, padx=0, pady=10)


            def edit_scores():
                def select_student():
                    selected_student = student_var.get()
                    # Retrieve the student information from the CSV file
                    with open('studentscores.csv', 'r') as f:
                        reader = csv.reader(f)
                        for row in reader:
                            if row[0] == selected_student:
                                student_info = row
                                break
                    # Open the edit screen and populate the fields with the student information
                    edit_scores_window = tk.Tk()
                    edit_scores_window.geometry("50x500")
                    edit_scores_window.title("Edit Scores")

                    full_name_label = tk.Label(edit_scores_window, text="Full Name:")
                    full_name_label.grid(row=0, column=0)
                    full_name_entry = tk.Entry(edit_scores_window)
                    full_name_entry.insert(0, student_info[0])
                    full_name_entry.grid(row=0, column=1)

                    score1_label = tk.Label(edit_scores_window, text="Score 1:")
                    score1_label.grid(row=1, column=0)
                    score1_entry = tk.Entry(edit_scores_window)
                    score1_entry.insert(0, student_info[1])
                    score1_entry.grid(row=1, column=1)

                    # Create the rest of the fields for the other scores and the submit button
                    ...

                    edit_scores_window.mainloop()

                teacher_window = tk.Tk()
                teacher_window.geometry("200x200")
                teacher_window.title("Edit Student Scores")

                student_var = tk.StringVar()

                # Create a list of student names from the CSV file
                student_names = []
                with open('studentscores.csv', 'r') as f:
                    reader = csv.reader(f)
                    for row in reader:
                        student_names.append(row[0])

                # Create a dropdown menu to display the student names
                student_dropdown = tk.OptionMenu(teacher_window, student_var, *student_names)
                student_dropdown.pack()

                # Create a button to submit the selection
                submit_button = tk.Button(teacher_window, text="Edit", command=select_student)
                submit_button.pack()



            def delete_scores():
                selected = listbox.get(listbox.curselection())
                confirmation = msgbox.askyesno("Delete", "Are you sure you want to delete this student?")
                if confirmation:
                    listbox.delete(listbox.curselection())
                    for student in students:
                        if selected == student[0]:
                            students.remove(student)
                    full_name.config(text="")
                    score1.config(text="")
                    score2.config(text="")
                    score3.config(text="")
                    score4.config(text="")
                    score5.config(text="")
                    score6.config(text="")
                    with open("studentscores.csv", "w", newline='') as file:
                        writer = csv.writer(file)
                        writer.writerows(students)
                else:
                    msgbox.showinfo("Deletion Cancelled", "The deletion has been cancelled.")

            add_button = tk.Button(teacher_window, text="Add", command=add_scores, font=("Arial", 12, "bold"))
            add_button.config(width=7, height=3)
            add_button.pack()

            edit_button = tk.Button(teacher_window, text="Edit", command=edit_scores, font=("Arial", 12, "bold"))
            edit_button.config(width=7, height=3)
            edit_button.pack()

            delete_button = tk.Button(teacher_window, text="Delete", command=delete_scores, font=("Arial", 12, "bold"))
            delete_button.config(width=7, height=3)
            delete_button.pack()

            listbox = tk.Listbox(on_select)
            listbox.pack()

        display_student_info()

    window = tk.Tk()
    window.geometry("300x300")
    window.title("Maths Scores")

    background_image = PhotoImage(file="Mathsimage.png")
    background_label = tk.Label(window, image=background_image)
    background_label.place(x=0, y=50, relwidth=1, relheight=1)

    student_button = tk.Button(window, text="Student", command=student_button_clicked, font=("Arial", 12, "bold"), highlightthickness=1)
    student_button.config(width=7, height=3)
    student_button.grid(row=0, column=0, padx=10, pady=10)

    teacher_button = tk.Button(window, text="Teacher", command=teacher_button_clicked, font=("Arial", 12, "bold"), highlightthickness=1)
    teacher_button.config(width=7, height=3)
    teacher_button.grid(row=0, column=1, padx=10, pady=10)

    admin_button = tk.Button(window, text="Admin", command=admin_button_clicked, font=("Arial", 12, "bold"), highlightthickness=1)
    admin_button.config(width=7, height=3)
    admin_button.grid(row=0, column=3, padx=10, pady=10)

    window.mainloop()
main_window_function()
