# python_win_redist

Build 64-bit Windows installers for Python 3.9 from source.

## Current releases:

* [3.9.16](https://github.com/xenago/python_win_redist/releases/tag/UserBuild_2022.12.07_19-41)
  * [python-3.9.16-amd64-full.exe](https://github.com/xenago/python_win_redist/releases/download/UserBuild_2022.12.07_19-41/python-3.9.16-amd64-full.exe)
  * [python-3.9.16-amd64.exe](https://github.com/xenago/python_win_redist/releases/download/UserBuild_2022.12.07_19-41/python-3.9.16-amd64.exe)
* [3.9.14](https://github.com/xenago/python_win_redist/releases/tag/UserBuild_2022.09.28_05-04)
  * [python-3.9.14-amd64-full.exe](https://github.com/xenago/python_win_redist/releases/download/UserBuild_2022.09.28_05-04/python-3.9.14-amd64-full.exe)
  * [python-3.9.14-amd64.exe](https://github.com/xenago/python_win_redist/releases/download/UserBuild_2022.09.28_05-04/python-3.9.14-amd64.exe)

## Motivation

At a certain point, supported Python versions begin to receive security updates without installers, so one must build the installer from source to upgrade an existing install.

Many of those installers are built and available here in [@adang1345's repo](https://github.com/adang1345/PythonWindows) if you don't need to build one from source yourself (e.g. by forking this repository).

That repository was a very useful resource. Some highlights:

* The Python 3.9 section in [`Notes.txt`](https://github.com/adang1345/PythonWindows/blob/master/Notes.txt)
* Several small patches were recreated from that repository
  * Building for release
  * Enabling debug symbols/binaries
  * Working around an https/http inconsistency
  * Did not adopt the fix for formatting of help .chm files as this is low-priority
* [Discussion in the issues](https://github.com/adang1345/PythonWindows/issues/4#issuecomment-1004194012) regarding building the full installer

## Notes

Server 2019 is used, as the Server 2022 image causes an error:

`MSB8020: The build tools for Visual Studio 2015 (Platform Toolset = 'v140') cannot be found. To build using the v140 build tools, please install Visual Studio 2015 build tools.  Alternatively, you may upgrade to the current Visual Studio tools by selecting the Project menu or right-click the solution, and then selecting "Retarget solution". [C:\venv\Tools\msi\bundle\bootstrap\pythonba.vcxproj]`

## Useful References

* https://github.com/adang1345/PythonWindows
* https://devguide.python.org/getting-started/setup-building/#windows
* https://github.com/python/cpython/blob/3.8/PCbuild/readme.txt
