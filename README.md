# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:

## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"
~~~
mkdir my-folder
~~~

## COMMAND AND OUTPUT
<img width="762" height="381" alt="image" src="https://github.com/user-attachments/assets/75a690a7-90c5-4f41-8ee0-75b119674d0e" />


Remove the directory "my-folder"
~~~
rmdir my-folder
~~~
## COMMAND AND OUTPUT
 <img width="674" height="275" alt="image" src="https://github.com/user-attachments/assets/bfbc8e18-b8ce-4f36-a172-9d7f929c4070" />

Create the file Rose.txt
~~~
COPY CON Rose.txt
A clock in a office can never get stolen
Too many employees watch it all the time
^Z
1 file(s) copied
~~~

## COMMAND AND OUTPUT
<img width="523" height="238" alt="image" src="https://github.com/user-attachments/assets/d765e9e7-634d-4c81-afcc-1d4bb6600b38" />


Create the file hello.txt using echo and redirection
~~~

echo “hello world” > hello.txt
type hello.txt
~~~

## COMMAND AND OUTPUT
<img width="599" height="256" alt="image" src="https://github.com/user-attachments/assets/2266dcf5-c7e2-41c1-a612-38bac5a2095e" />


Copy the file hello.txt into the file hello1.txt
~~~

copy hello.txt hello1.txt
~~~

## COMMAND AND OUTPUT
<img width="516" height="127" alt="image" src="https://github.com/user-attachments/assets/0118d272-95f2-4f7e-95ae-f725c44ec0f4" />


Remove the file hello1.txt

~~~

del hello1.txt
~~~
## COMMAND AND OUTPUT
<img width="482" height="309" alt="image" src="https://github.com/user-attachments/assets/d84a078e-e464-4482-810c-94c3c6fa943c" />


List out the file hello1.txt in the current directory
~~~
dir hello1.txt
~~~

## COMMAND AND OUTPUT
<img width="482" height="309" alt="image" src="https://github.com/user-attachments/assets/d84a078e-e464-4482-810c-94c3c6fa943c" />



List out all the associated file extensions 
~~~
assoc | more
~~~

## COMMAND AND OUTPUT
<img width="463" height="327" alt="image" src="https://github.com/user-attachments/assets/718c1a1d-c175-479a-8abb-d3a717ce189a" />

Compare the file hello.txt and rose.txt
~~~
fc hello.txt Rose.txt
~~~

## COMMAND AND OUTPUT
<img width="525" height="245" alt="image" src="https://github.com/user-attachments/assets/f1171bb8-6001-46e0-99b8-bce3e729a470" />

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".
~~~
@echo off
set name=John
echo Hello, %name%!
pause

Execute the batch file 1.bat
~~~




## OUTPUT
<img width="521" height="191" alt="image" src="https://github.com/user-attachments/assets/672b524d-d1cb-487b-a412-4ae6f838e447" />



Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.
~~~
@echo off
:main
set /p number=Enter a number: 
rem Calculate remainder when divided by 2
set /a remainder=%number% %% 2
if %remainder%==1 (
    echo %number% is an odd number.
) else (
    echo %number% is not an odd number.
)
:choice
set /p continue=Do you want to check another number? (Y/N): 
if /i "%continue%"=="Y" goto main
if /i "%continue%"=="N" goto end
echo Invalid choice, please enter Y or N.
goto choice
:end
echo Thank you for using the odd number checker!
pause
~~~

## OUTPUT

<img width="602" height="330" alt="image" src="https://github.com/user-attachments/assets/8283b51e-b583-4464-aeb4-f61910d386f8" />



Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.
~~~
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause
~~~



## OUTPUT

<img width="412" height="175" alt="image" src="https://github.com/user-attachments/assets/7f523d15-e268-4052-bef9-96680e7713da" />




Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):

~~~
@echo off
if exist sample.txt (
    echo sample.txt exists.
) else (
    echo sample.txt does not exist.
)
pause
~~~
## OUTPUT
<img width="785" height="240" alt="image" src="https://github.com/user-attachments/assets/3c29c0c1-42d4-4fa5-8a0f-2bda49981cca" />



Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.
~~~
@echo off
:menu
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
set /p choice=Choose an option: 
if "%choice%"=="1" goto hello
if "%choice%"=="2" goto createfile
if "%choice%"=="3" goto end

:hello
echo Hello, World!
goto menu

:createfile
echo Creating a file...
echo This is a new file > newfile.txt
goto menu
:end
echo Goodbye!
pause
~~~
## OUTPUT
<img width="533" height="425" alt="image" src="https://github.com/user-attachments/assets/e4a6f044-20b7-4e89-b689-4519b5f539d1" />




# RESULT:
The commands/batch files are executed successfully.

