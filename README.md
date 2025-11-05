#labsheet-7 
1. Crs1and write text into a file
def write_file():
    with open("sample.txt", "w") as f:
        f.write("Hello, this is a test file.\nWelcome to Python file handling!")
    print("File written successfully."y.
# 2. Read entire content of a text file
def read_entire_file():
    with open("sample.txt", "r") as f:
        print(f.read())

# 3. Read a file line by line
def read_line_by_line():
    with open("sample.txt", "r") as f:
        for line in f:
            print(line.strip())

# 4. Count number of words in a text file
def count_words():
    with open("sample.txt", "r") as f:
        words = f.read().split()
    print("Total words:", len(words))

# 5. Count number of lines and characters in a file
def count_lines_chars():
    with open("sample.txt", "r") as f:
        lines = f.readlines()
    print("Lines:", len(lines))
    print("Characters:", sum(len(line) for line in lines))

# 6. Display only even-numbered lines from a file
def even_numbered_lines():
    with open("sample.txt", "r") as f:
        lines = f.readlines()
    for i in range(1, len(lines), 2):
        print(lines[i].strip())

# 7. Write multiple lines of input from the user into a file
def write_multiple_lines():
    with open("multi.txt", "w") as f:
        print("Enter multiple lines (type 'stop' to end):")
        while True:
            line = input()
            if line.lower() == "stop":
                break
            f.write(line + "\n")
    print("Lines written successfully.")

# 8. Append new content to an existing file
def append_file():
    with open("sample.txt", "a") as f:
        f.write("\nThis is an appended line.")
    print("Content appended successfully.")

# 9. Copy contents of one file into another
def copy_file():
    with open("sample.txt", "r") as src, open("copy.txt", "w") as dest:
        dest.write(src.read())
    print("File copied successfully.")

# 10. Read a file and convert its content to uppercase
def file_to_uppercase():
    with open("sample.txt", "r") as f:
        content = f.read().upper()
    print(content)

# 11. Search for a particular word in a file
def search_word():
    word = input("Enter word to search: ")
    with open("sample.txt", "r") as f:
        content = f.read()
    if word in content:
        print(f"'{word}' found in file.")
    else:
        print(f"'{word}' not found.")

# 12. Count occurrence of a specific word in a file
def count_word_occurrence():
    word = input("Enter word to count: ")
    with open("sample.txt", "r") as f:
        content = f.read().split()
    print(f"'{word}' occurs {content.count(word)} times.")

# 13. Read numbers from a file and display sum and average
def sum_and_average():
    with open("numbers.txt", "r") as f:
        numbers = list(map(int, f.read().split()))
    print("Sum:", sum(numbers))
    print("Average:", sum(numbers) / len(numbers))

# 14. Display the longest line in a file
def longest_line():
    with open("sample.txt", "r") as f:
        lines = f.readlines()
    print("Longest line:", max(lines, key=len).strip())

# 15. Replace a word in a file with another word
def replace_word():
    old = input("Word to replace: ")
    new = input("New word: ")
    with open("sample.txt", "r") as f:
        content = f.read().replace(old, new)
    with open("sample.txt", "w") as f:
        f.write(content)
    print("Word replaced successfully.")

# 16. Display first and last lines of a file
def first_last_lines():
    with open("sample.txt", "r") as f:
        lines = f.readlines()
    print("First line:", lines[0].strip())
    print("Last line:", lines[-1].strip())

# 17. Remove blank lines from a file
def remove_blank_lines():
    with open("sample.txt", "r") as f:
        lines = [line for line in f if line.strip()]
    with open("sample.txt", "w") as f:
        f.writelines(lines)
    print("Blank lines removed.")

# 18. Store unique words into another file
def unique_words():
    with open("sample.txt", "r") as f:
        words = set(f.read().split())
    with open("unique.txt", "w") as f:
        f.write(" ".join(words))
    print("Unique words stored successfully.")

# 19. Sort all words alphabetically and save to new file
def sort_words():
    with open("sample.txt", "r") as f:
        words = sorted(f.read().split())
    with open("sorted.txt", "w") as f:
        f.write(" ".join(words))
    print("Words sorted and saved.")

# 20. Merge two text files into a third file
def merge_files():
    with open("sample.txt", "r") as f1, open("multi.txt", "r") as f2, open("merged.txt", "w") as out:
        out.write(f1.read() + "\n" + f2.read())
    print("Files merged successfully.")

# 21. Create and write data into a CSV file
def write_csv():
    with open("students.csv", "w", newline='') as f:
        writer = csv.writer(f)
        writer.writerow(["Name", "Marks"])
        writer.writerows([["Amit", 85], ["Vidhi", 92], ["Rahul", 78]])
    print("CSV file created and written.")

# 22. Read data from a CSV file and display it
def read_csv():
    with open("students.csv", "r") as f:
        reader = csv.reader(f)
        for row in reader:
            print(row)

# 23. Calculate average of numeric columns in CSV
def avg_csv():
    with open("students.csv", "r") as f:
        reader = csv.DictReader(f)
        marks = [int(row["Marks"]) for row in reader]
    print("Average Marks:", sum(marks) / len(marks))

# 24. Count number of rows and columns in a CSV
def count_rows_columns():
    with open("students.csv", "r") as f:
        reader = list(csv.reader(f))
        print("Rows:", len(reader))
        print("Columns:", len(reader[0]))

# 25. Append new record to an existing CSV file
def append_csv():
    with open("students.csv", "a", newline='') as f:
        writer = csv.writer(f)
        name = input("Enter name: ")
        marks = input("Enter marks: ")
        writer.writerow([name, marks])
    print("Record appended successfully.")

# 26. Copy data from one CSV file to another
def copy_csv():
    with open("students.csv", "r") as src, open("copy_students.csv", "w", newline='') as dest:
        for line in src:
            dest.write(line)
    print("CSV copied successfully.")

# 27. Display specific columns (Name, Marks) from CSV
def display_specific_columns():
    with open("students.csv", "r") as f:
        reader = csv.DictReader(f)
        for row in reader:
            print(row["Name"], "-", row["Marks"])

# 28. Display highest marks from a CSV file
def highest_marks():
    with open("students.csv", "r") as f:
        reader = csv.DictReader(f)
        data = list(reader)
        top = max(data, key=lambda x: int(x["Marks"]))
    print("Topper:", top["Name"], "with", top["Marks"], "marks.")

# 29. Search a record by student name
def search_student():
    name = input("Enter name to search: ")
    with open("students.csv", "r") as f:
        reader = csv.DictReader(f)
        found = False
        for row in reader:
            if row["Name"].lower() == name.lower():
                print(row)
                found = True
        if not found:
            print("Record not found.")

# 30. Combine multiple CSV files into one
def combine_csv():
    files = ["students.csv", "copy_students.csv"]
    with open("combined.csv", "w", newline='') as out:
        writer = None
        for file in files:
            with open(file, "r") as f:
                reader = csv.reader(f)
                header = next(reader)
                if writer is None:
                    writer = csv.writer(out)
                    writer.writerow(header)
                writer.writerows(reader)
    printnt("CSV files combines successful")SV
