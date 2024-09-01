# Real-time-Language-Translator
This project focuses on translation input text into the desired language in real-time.
Description: Line by Line explanation of code.

**Importing Necessary Modules:**
The python libraries used in this particular project are: 1. tkinter  2. googletrans
First install the necessary module: pip install googletrans==4.0.0-rc1
This command will install the latest version of googletrans. It is the python library which uses the Google Translate API to transalate the text entered by the user. After the installation, import ttk from tkinter which provides themed widgets that offer a modern look and feel (like 'Combobox' which we used in this code). Next import Translator, LANGUAGES from googletrans. 'Translator' is a class that provides methods to translate text. 'LANGUAGES' is a dictionary that maps language codes (like 'en' for English) to their full names (like 'English').

**Creating the Main Window:**
root = Tk() creates the main window for the application. root.geometry('1100x320') sets the dimensions (width x height) of the main window to 1100 pixels wide and 320 pixels high. 
Label(root, text="Language Translator", font="Arial 20 bold", bg='yellow'): Label is a widget that displays text on the GUI. 'root' specifies the parent window. '.pack()' method organizes the widget in blocks before placing them in the parent widget (root).

**Input and Output Fields**: 
Label(root, text="Input Text", font='arial 13 bold', bg='yellow'): Creates a label that reads "Input Text" with font size 13 and bold weight, and a yellow background.
.place(x=165, y=90): The place method positions the label at coordinates (165, 90) in the window. Output_text = Text(root, font='arial 10', height=5, wrap=WORD, padx=5, pady=5, width=50): Text is a widget that allows multi-line text input/output. font='arial 10' sets the font style and size. 'height=5' specifies the number of text lines visible. 'wrap=WORD' wraps the text by word. 'padx=5', 'pady=5' adds internal padding for the text box. 'width=50' sets the width of the text box.

**Language Selection:**
Language = list(LANGUAGES.values()): Converts the dictionary values (language names) from LANGUAGES to a list for use in the Combobox.
dest_lang = ttk.Combobox(root, values=language, width=22): ttk.Combobox is a dropdown widget that allows selection from a list of values.
values=language sets the list of values (languages) to choose from.
width=22 sets the width of the dropdown.
dest_lang.place(x=600, y=250): Positions the Combobox at coordinates (600, 250).

**Defining the Translation Function:**
def Translate():: Defines a function named Translate that will be executed when the "Translate" button is clicked.
'try:': Starts a try block to handle exceptions.
translator = Translator(): Creates an instance of the Translator class to access the translation functions.
translation = translator.translate(Input_text.get(), dest=dest_lang.get()):
Input_text.get(): Retrieves the text entered in the input entry widget.
dest=dest_lang.get(): Gets the selected destination language from the Combobox.
translator.translate(): Calls the translate method to perform the translation.
Output_text.delete(1.0, END): Clears the output text widget from the first character (1.0) to the end (END).
Output_text.insert(END, translation.text): Inserts the translated text at the end of the Output_text widget.
except Exception as e:: Catches any exceptions raised during the translation process.
print(f"Translation error: {e}"): Prints an error message if an exception occurs.

**Creating the Translate Button:**
Button: Creates a clickable button widget. command=Translate: Associates the Translate function with the button click.

**Start the Tkinter Event Loop:**
root.mainloop(): Starts the Tkinter event loop, which waits for user interaction and keeps the application running. This is essential to display the GUI and handle events like button clicks.

By understanding each line and word in this code, you get a comprehensive view of how a Python-based GUI language translator works using tkinter and googletrans.

**NOTE:** First 'run pip install googletrans==4.0.0-rc1' command and then import the modules.
