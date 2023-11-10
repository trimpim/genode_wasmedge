To ensure patching works you should have the patch from #67.

replace `trimpim` with your depot user name in:
 - llvm/used_apis
 - spdlog/used_apis
 - wasmedge/used_apis
 - wasmedge/pkg/wasmedge/archives

To build use the following commands:

```
goa -C llvm build-dir
goa -C llvm export --depot-user <your_depot_user>
goa -C spdlog export --depot-user <your_depot_user>
goa -C wasmedge export --depot-user <your_depot_user>

goa -C wasmedge run
```

The expected output is:
```
[init -> wasmedge -> wasmedge] lwIP Nic interface down
[init -> wasmedge -> wasmedge] Warning: pathconf: pathconf not implemented
[init -> wasmedge -> wasmedge] new connection at 80
[init -> wasmedge -> wasmedge] Warning: read blocked until lwIP interface is ready
```
