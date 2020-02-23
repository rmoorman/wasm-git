WASM-GIT
========
(WASM should be pronounced like `awesome` starting with a `W` ).

GIT for nodejs and the browser using [libgit2](https://libgit2.org/) compiled to WebAssembly with [Emscripten](https://emscripten.org).

**This is dependent on mmap fixes in emscripten:**

- https://github.com/emscripten-core/emscripten/pull/10095
- https://github.com/emscripten-core/emscripten/pull/10526


The script in [build.sh](build.sh) shows how to configure and build, and you'll find the resulting lg2.js/lg2.wasm under the generated `examples` folder.

An example of interacting with libgit2 from nodejs can be found in [examples/example_node.js](example_node.js).

An example for the browser (using webworkers) can be found in [examples/example_webworker.js](example_webworker.js). You can start a webserver for this by running the [webserverwithgithubproxy.js](webserverwithgithubproxy.js) script, which will launch a http server at http://localhost:5000 with a proxy to github. Proxy instead of direct calls is needed because of CORS restrictions in a browser environment.
