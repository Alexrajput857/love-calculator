from tkinter import *
import random

# Function to calculate love percentage
def calculate_love():
    # Get the names from the input fields
    name1_value = name1.get().strip()
    name2_value = name2.get().strip()
    
    # Validate the inputs
    if not name1_value or not name2_value:
        result.config(text="Please enter both names!", fg="red")
        return
    
    # Generate a "love percentage" using a hash-like combination
    combined = name1_value.lower() + name2_value.lower()
    love_score = sum(ord(char) for char in combined) % 101
    
    # Display the result
    result.config(
        text=f"Love Percentage between {name1_value} and {name2_value}: {love_score}%",
        fg="green"
    )

# Creating GUI window
root = Tk()
root.geometry('400x300')
root.title('Love Calculator ❤️')

# Heading on Top
heading = Label(
    root, 
    text='Love Calculator - How much are you into each other?', 
    font=('Arial', 14, 'bold'),
    fg='dark red'
)
heading.pack(pady=10)

# Slot/input for the first name
slot1 = Label(root, text="Aapan Naam Dala:", font=('Arial', 10))
slot1.pack()
name1 = Entry(root, border=3, font=('Arial', 10))
name1.pack(pady=5)

# Slot/input for the partner name
slot2 = Label(root, text="Aapan Madam Jii Ke Naam Dala:", font=('Arial', 10))
slot2.pack()
name2 = Entry(root, border=3, font=('Arial', 10))
name2.pack(pady=5)

# Button to calculate love percentage
bt = Button(
    root, 
    text="Calculate ❤️", 
    height=2, 
    width=15, 
    bg='pink', 
    fg='black',
    font=('Arial', 10, 'bold'),
    command=calculate_love
)
bt.pack(pady=10)

# Label to display the result
result = Label(root, text='', font=('Arial', 12, 'bold'))
result.pack(pady=10)

# Starting the GUI
root.mainloop()
# love-calculator
