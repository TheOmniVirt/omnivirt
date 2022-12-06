Build omnivirtd.exe:

```
pyinstaller -w -F .\omnivirt\omnivirtd.py  --hidden-import=eventlet.hubs.epolls --hidden-import=eventlet.hubs.kqueue --hidden-import=eventlet.hubs.selects --collect-all os_win --collect-all wmi --collect-all PyMI -i .\etc\images\favicon.ico
```

Build cli.exe:

```
pyinstaller -c -F .\omnivirt\cli.py  --hidden-import=eventlet.hubs.epolls --hidden-import=eventlet.hubs.kqueue --hidden-import=eventlet.hubs.selects  -i .\etc\images\favicon.ico
```

Build protoc files:

```
python -m grpc_tools.protoc -I../services --python_out=. --grpc_python_out=. control.proto
```