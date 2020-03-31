# Common_Errors_Anaconda_(Windows 10)
## Error 01:
* While trying to convert .ui file into .py file, it gave me (ImportError: DLL load failed)
- [x] Solution that worked for me: 
    - Run the anaconda prompt as an Administrator
    - Go to the directory where you've installed anconda in (ex: cd c:/Users/Hosna/Anaconda_Install)
    - write this command `<python -m pip install --upgrade pyqt5>`
    - After this finish, try to convert your .ui file into .py using this command `<pyuic5 -x your_file_name.ui -o your_file_name.py>` (ex: pyuic5 -x first_app.ui -o first_app.py)

##### Note: other proposed solution is: search for the file (python3.dll) in the directory of anaconda, copy and paste it at the directory of PyQt5 (ex: Anaconda_Install -> Lib -> site-pkgs -> PyQt5 -> paste the .dll file here)

## Error 02:
* Spyder isn't launching and Anaconda navigator keeps telling to update it but when I click "yes" to update nothing happens
- :+1: Solution that worked for me