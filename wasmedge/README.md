The http_server directory contains the sources to build the wasm app
used in the package.

 1) build it as described in the http_server sub directory
 2) copy its output to 'raw/app.wasm`
    ```
    cp http_server/target/wasm32-wasi/release/http_server.wasm raw/app.wasm
    ```
 3) update `raw/app.tar` as follows:
    ```
    cd raw
    tar cf app.tar app.wasm
    ```
 4) test this app:
    ```
    # make sure your linux tap devices are configured correctly
    goa run
    # in different terminal:
    curl -X POST http://169.254.71.254:80 -d 'name=Hello Gapfruit Dev'
    ```
