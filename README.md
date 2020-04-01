# Common_Errors_Anaconda_(Windows 10)
## Error 01:
* While trying to convert .ui file into .py file, it gave me (ImportError: DLL load failed)
- :+1: Solution that worked for me: 
    - Run the anaconda prompt as an Administrator
    - Go to the directory where you've installed anconda in *(ex: cd c:/Users/Hosna/Anaconda_Install)*
    - write this command `<python -m pip install --upgrade pyqt5>`
    - After this finish, try to convert your .ui file into .py using this command `<pyuic5 -x your_file_name.ui -o your_file_name.py>` *(ex: pyuic5 -x first_app.ui -o first_app.py)*

##### Note: other proposed solution is: search for the file (python3.dll) in the directory of anaconda, copy and paste it at the directory of PyQt5 (ex: Anaconda_Install -> Lib -> site-pkgs -> PyQt5 -> paste the .dll file here)

## Error 02:
*  Anaconda navigator keeps telling to update it but when I click "yes" to update nothing happens
- :+1: Solution that worked for me:
    - Just run Anaconda navigator as administrator.
    - **Or** you may update it manually from the anconda prompt run this command: `<conda update --all>`

## Error 03:
* Trying to uninstall/install any package gives this error\
[WinError 127] The specified procedure could not be found\
[WinError 127] The specified procedure could not be found
- :+1: Solution that worked for me:
    - *Said by "SimonCarozza" [here](https://github.com/conda/conda/issues/9003)*
    > I found out libssl-1_1-x64 dlls in Anaconda/DLLS and Anaconda/Library/bin being installed at different dates, so, as an experiment, I copied the one in Anaconda/DLLS and replaced that in Anaconda/Library/bin and conda started working again, at least for now - I could install new packages again.
   
## Error 04:
* Spyder doesn't launch
    - "python stopped working" diaglog box
        -  Error opening Anaconda or spyder "no Qt plugin platform" 
* These errors happened in series to me, whenever I try to solve one the other would just appear(It just missed up more not solved)
* Proposed solutions:
    - run this command in anaconda prompt `<spyder --reset>` then restart your pc
    - update anconda or pyqt only `<conda update --all>`    `<conda update pyqt>`
    - Uninstall pyqt and qt then reinstall them again `<conda remove qt>`     `<conda install -c anaconda qt>` 

