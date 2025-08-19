# File-handling-and-exception-handling-assignment-week-4
def python_assignment_reader():
    # The assignment file to read
    input_file = "assignment.py"

    try:
        # Open and read the file
        with open(input_file, "r") as f:
            lines = f.readlines()

        # Add comments at the end of each line to show line numbers
        modified_lines = [line.rstrip("\n") + f"   # Line {i+1}\n" for i, line in enumerate(lines)]

        # Output file
        output_file = "modified_assignment.py"

        # Write modified version
        with open(output_file, "w") as f:
            f.writelines(modified_lines)

        print(f"✅ Modified assignment saved as '{output_file}'")

    except FileNotFoundError:
        print("❌ Error: The file 'assignment.py' does not exist.")
    except PermissionError:
        print("❌ Error: You don’t have permission to access this file.")
    except Exception as e:
        print(f"⚠️ Unexpected error: {e}")

