# Common_Errors_Anaconda_(Windows 10)
## Error 01:
* While trying to convert .ui file into .py file, it gave me (ImportError: DLL load failed)
- :+1: Solution that worked for me: 
    - Run the anaconda prompt as an Administrator.
    - Go to the directory where you've installed anconda in. *(ex: cd c:/Users/Hosna/Anaconda_Install)*
    - write this command: `python -m pip install --upgrade pyqt5`
    - After this finish, try to convert your .ui file into .py using this command: `pyuic5 -x your_file_name.ui -o your_file_name.py` *(ex: pyuic5 -x first_app.ui -o first_app.py)*

##### Note: other proposed solution is: search for the file (python3.dll) in the directory of anaconda, copy and paste it at the directory of PyQt5 (ex: Anaconda_Install -> Lib -> site-pkgs -> PyQt5 -> paste the .dll file here)

## Error 02:
*  Anaconda navigator keeps telling to update it but when I click "yes" to update nothing happens.
- :+1: Solution that worked for me:
    - Just run Anaconda navigator as administrator.
    - **Or** you may update it manually from the anconda prompt run this command: `conda update --all`

## Error 03:
* Trying to uninstall/install any package gives this error:\
[WinError 127] The specified procedure could not be found\
[WinError 127] The specified procedure could not be found
- :+1: Solution that worked for me:
    - *Said by "SimonCarozza" [here](https://github.com/conda/conda/issues/9003)*
    > I found out libssl-1_1-x64 dlls in Anaconda/DLLS and Anaconda/Library/bin being installed at different dates, so, as an experiment, I copied the one in Anaconda/DLLS and replaced that in Anaconda/Library/bin and conda started working again, at least for now - I could install new packages again.

## Error 04:
* whenever I try to write anything in the prompt regarding anaconda it gives this error:\
 CondaHTTPError: HTTP 000 CONNECTION FAILED for url <https://conda.anaconda.org/conda-forge/win-64/current_repodata.json>\
  Elapsed: - \
  An HTTP error occurred when trying to retrieve this URL.\
  HTTP errors are often intermittent, and a simple retry will get you on your way.\
  'https://conda.anaconda.org/conda-forge/win-64' 
- :+1: solution that worked for me:
    - *said by "kevin-keraudren" [here](https://github.com/conda/conda/issues/6007)*
    >  You can download the packages manually using your web browser, for instance: [this link](https://anaconda.org/anaconda/openssl/files)\
        Then install packages offline:\
        `conda install --offline openssl-1.1.1c-he774522_1.tar.bz2`  (note to take the exact name of the winrar that will be downloaded after the word "offline")

## Error 05:
* Spyder doesn't launch but Anaconda navigator works.
    - Spyder opens for seconds then error "python stopped working"
        -  Error opening Anaconda or spyder "no Qt plugin platform" 
* :sob: These errors happened in series to me, whenever I try to solve one the other would just appear (missed up more)
* Proposed solutions:
    - run this command in anaconda prompt: `spyder --reset` then restart your pc.
    - update anconda or pyqt (try both): `conda update --all`    `conda update pyqt`
    - Uninstall pyqt and qt then reinstall them again `<conda remove qt>` then   `<conda install -c anaconda qt>` 

* :+1: Solution that worked for me:
    - :disappointed: So frustrating, but actually after trying all these solutions
    I kept into facing more problems and\
    at last I gave up and **Unistalled** Anaconda then **Reinstalled** it and it worked again. 

##### Note: at first when spyder didn't launch, I tried to run it from anaconda navigator but it yielded this error: (from PyQt5.QtWebEngineWidgets import QWebEnginePage, ValueError: PyCapsule_GetPointer called with incorrect name). [Link](https://github.com/spyder-ide/spyder/issues/3138) that mentioned same issue in the comments.

### Note: It's really important to have more than one environment in python.

## Error 06: 
* Error in github desktop make me unable to push anything, the error is like the one in this [link](https://github.com/desktop/desktop/issues/2623) and the solution is on the same link, I'm just rephrasing it.
* :+1: Solution that worked for me:
    - From search/start at window, type registry editor and open it.
    - Choose HKEY_CURRENT_USER\Software\Microsoft\Command Processor\
    - If you find an AutoRun key then delete it.
        - In my case, this autorun key was from the uninstalled and delected anaconda directory.

## Error 07:
* Python crashes whenever I try to install anything through anaconda prompt.\ "Python has stopped working" dialog box appears just after solving the environment.
* Proposed solutions:
    - Some proposed that: it's for your antivirus is blocking python so turn it off for some time.
    - Others said to remove conda-forge then add it again. `conda config --remove channels conda-forge` then `conda config --add channels conda-forge`
    - Another solution was to set the channel_priority to false with this command `conda config --set channel_priority false`
    - Also, there was to update conda `conda update --all`

* :+1: Solution that worked for me:
    - I thought that the anaconda that I've got by this time is corrupted with these errors
    and so I uninstalled it, removed it totally and downloaded it from their official website.
    - When I faced this problem again just after installing anaconda, updating conda using the above command solved the issue.
    - **Useful links for this issue** that have mentioned the above solutions: [Link1](https://github.com/conda/conda/issues/8051), [link2](https://github.com/conda/conda/issues/6406)

## Error 08:
* Trying to install tensorflow on anaconda gives me this error:  `Access is denied: (*path*) Consider using the `--user` option or check the permissions.`
* :+1: Solution that worked for me:
    - My anaconda was installed on `d: drive` meanwhile the prompt was from the `c: drive` so I only needed to `cd` to `d:`

## Note for Error 09:
* If you're gonna install spyder/python and Rstudio, then better separate them into two different environment, as probably both will conflict together.
