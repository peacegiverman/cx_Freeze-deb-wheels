# cx_Freeze 5 for Debian/Ubuntu
cx_Freeze 5 creates broken binaries on Debian-based distros. If you build a binary with cx_Freeze on Debian or Ubuntu and try to run it, you will get this error:

    Fatal Python error: Py_Initialize: Unable to get the locale encoding
    ImportError: No module named 'encodings'
    Aborted (core dumped)

I have submitted a patch for this issue upstream and will provide a couple of patched wheels until they land in PyPI. To install the wheels just run:
    pip install /path/to/cx_Freeze-5.0.1-<YOUR-VERSION>-linux_x86_64.whl

## Patching cx_Freeze ##

If the wheels aren't working for you, or if you are using a different version of Python, you can apply the patch from this repository and build cx_Freeze manually. You can do so like this:

    pip install cx-Freeze -d /path/to/cx-Freeze
    cd /path/to/cx-Freeze
    patch -p0 < cx_freeze-issue131.patch

Just remember to replace `/path/to/` with the correct path.
