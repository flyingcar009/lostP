Known issues

Special permissions (and Windows Vista or later) are required when cloning repositories with symbolic links, therefore support for symbolic links is disabled by default. Use git clone -c core.symlinks=true <URL> to enable it, see details here.
If configured to use Plink, you will have to connect with putty first and accept the host key.
Some console programs, most notably non-MSYS2 Python, PHP, Node and OpenSSL, interact correctly with MinTTY only when called through winpty (e.g. the Python console needs to be started as winpty python instead of just python).
cURL uses $HOME/_netrc instead of $HOME/.netrc.
If you specify command-line options starting with a slash, POSIX-to-Windows path conversion will kick in converting e.g. "/usr/bin/bash.exe" to "C:\Program Files\Git\usr\bin\bash.exe". When that is not desired -- e.g. "--upload-pack=/opt/git/bin/git-upload-pack" or "-L/regex/" -- you need to set the environment variable MSYS_NO_PATHCONV temporarily, like so:
MSYS_NO_PATHCONV=1 git blame -L/pathconv/ msys2_path_conv.cc
Alternatively, you can double the first slash to avoid POSIX-to-Windows path conversion.
Git for Windows will not allow commits containing DOS-style truncated 8.3-format filenames ending with a tilde and digit, such as mydocu~1.txt. A workaround is to call git config core.protectNTFS false, which is not advised. Instead, add a rule to .gitignore to ignore the file(s), or rename the file(s).
Many Windows programs (including the Windows Explorer) have problems with directory trees nested so deeply that the absolute path is longer than 260 characters. Therefore, Git for Windows refuses to check out such files by default. You can overrule this default by setting core.longPaths, e.g. git clone -c core.longPaths=true ....
Some commands are not yet supported on Windows and excluded from the installation.
As Git for Windows is shipped without Python support, all Git commands requiring Python are not yet supported; e.g. git p4.
The Quick Launch icon will only be installed for the user running setup (typically the Administrator). This is a technical restriction and will not change.
Should you encounter other problems, please search the bug tracker and the mailing list, chances are that the problem was reported already. If it has not been reported, please follow our bug reporting guidelines and report the bug.
Licenses

Git is licensed under the GNU Public License version 2.
Git for Windows also contains Embedded CAcert Root Certificates. For more information please go to https://www.cacert.org/policy/RootDistributionLicense.php.
This package contains software from a number of other projects including Bash, zlib, curl, msmtp, tcl/tk, perl, MSYS2 and a number of libraries and utilities from the GNU project, licensed under the GNU Public License. Likewise, it contains Perl which is dual licensed under the GNU Public License and the Artistic License.
Changes since Git for Windows v2.8.2 (May 3rd 2016)

New Features
Comes with Git v2.8.3.
Changes since Git for Windows v2.8.1 (April 4th 2016)

New Features
Comes with Git v2.8.2.
Starting with version 2.8.2, Git for Windows is also published as a NuGet package.
Comes with Git Credential Manager v1.3.0.
Bug Fixes
FSCache is now enabled by default even when upgrading from previous Git for Windows versions.
We now add git.exe to the PATH by default even when upgrading from previous Git for Windows versions.
Git GUI now sets author information correctly when amending.
OpenSSL received a critical update to version 1.0.2h.
Changes since Git for Windows v2.8.0 (March 29th 2016)

New Features
Comes with Git v2.8.1.
The Git for Windows project updated its contributor guidelines to the Contributor Covenant 1.4.
Bug Fixes
Git's default editor (vim) is no longer freezing in CMD windows.
GIT_SSH (and other executable paths that Git wants to spawn) can now contain spaces.
Changes since Git for Windows v2.7.4 (March 18th 2016)

New Features
Comes with Git v2.8.0.
Comes with the Git Credential Manager v1.2.2.
The FSCache feature (which was labeled experimental for quite some time) is now enabled by default.
Git is now added to the PATH by default (previously, the default was for Git to be available only from Git Bash/CMD).
The installer now offers to launch the Git Bash right away.
Bug Fixes
The previous workaround for the blurred link to the Git Credential Manager was fixed so that the link is neither blurry nor overlapping.
The installer now changes the label of the Next button to Install on the last wizard page before installing.
Changes since Git for Windows v2.7.3 (March 15th 2016)

New Features
Comes with Git 2.7.4.
Bug Fixes
The Git Credential Manager hyperlink in the installer is no longer blurred.
Changes since Git for Windows v2.7.2 (February 23rd 2016)

New Features
Git for Windows now ships with the Git Credential Manager for Windows.
Comes with Git v2.7.3.
Bug Fixes
We now handle UTF-8 merge and squash messages correctly in Git GUI.
When trying to modify a repository config outside of any Git worktree, git config no longer creates a .git/ directory but prints an appropriate error message instead.
A new version of Git for Windows' SDK was released.
We no longer show asterisks when reading the username for credentials.
Changes since Git for Windows v2.7.1(2) (February 12th 2016)

New Features
Git for Windows' SDK version 1.0.2 has been released.
The "list references" window of gitk is now wider by default.
Comes with Git 2.7.2.
Bug Fixes
The user is now presented with a nice error message when calling node while node.exe is not in the PATH (this bug also affected other interactive console programs such as python and php).
The arrow keys are respected again in gitk.