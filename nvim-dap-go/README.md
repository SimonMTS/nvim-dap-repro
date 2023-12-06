# nvim-dap-go

The following are reproduction steps using docker, you can of course just
manually run the commands from the dockerfile as well.

Run this command:
```
$ docker run --rm -it $(docker build -q .)
```

Then after nvim has started, wait for lazy to install everything and quit out
of it with `q`. Then run:
```
:lua require('dap-go').debug_test()
```

You should see the error:
```
starting debug session './. : nil'...
E5108: Error executing lua /root/.local/share/nvim/lazy/nvim-dap-go/lua/dap-go.lua:140: attempt to concatenate local '
testname' (a nil value)
stack traceback:
        /root/.local/share/nvim/lazy/nvim-dap-go/lua/dap-go.lua:140: in function 'debug_test'
        /root/.local/share/nvim/lazy/nvim-dap-go/lua/dap-go.lua:158: in function 'debug_test'
        [string ":lua"]:1: in main chunk
```
