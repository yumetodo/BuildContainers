
FROM    alpine:3.10
RUN apk add --no-cache zlib-dev openssl-dev git bash rust cargo nodejs npm && \
        npm update -g npm && \
        cargo install wasm-pack && \
# https://rustwasm.github.io/wasm-pack/book/prerequisites/non-rustup-setups.html
        wget https://static.rust-lang.org/dist/rust-std-1.34.2-wasm32-unknown-unknown.tar.gz && \
        tar -xf rust-std-1.34.2-wasm32-unknown-unknown.tar.gz && \
        mv rust-std-1.34.2-wasm32-unknown-unknown/rust-std-wasm32-unknown-unknown/lib/rustlib/wasm32-unknown-unknown /usr/lib/rustlib/ && \
        rm -r rust-std-1.34.2-wasm32-unknown-unknown && rm rust-std-1.34.2-wasm32-unknown-unknown.tar.gz
#  INFO 2019-09-09T16:55:21Z: wasm_pack::command: Running build command...
#  INFO 2019-09-09T16:55:21Z: wasm_pack::command::build: Checking rustc version...
#  INFO 2019-09-09T16:55:21Z: wasm_pack::command::build: rustc version is 34.
#  INFO 2019-09-09T16:55:21Z: wasm_pack::command::build: Checking crate configuration...
#  INFO 2019-09-09T16:55:21Z: wasm_pack::command::build: Crate is correctly configured.
#  INFO 2019-09-09T16:55:21Z: wasm_pack::command::build: Checking for wasm-target...
# [INFO]: Checking for the Wasm target...
#  INFO 2019-09-09T16:55:21Z: wasm_pack::build::wasm_target: Looking for wasm32-unknown-unknown in "/usr/lib/rustlib"
#  INFO 2019-09-09T16:55:21Z: wasm_pack::build::wasm_target: Found wasm32-unknown-unknown in "/usr/lib/rustlib"
#  INFO 2019-09-09T16:55:21Z: wasm_pack::command::build: Checking for wasm-target was successful.
#  INFO 2019-09-09T16:55:21Z: wasm_pack::command::build: Building wasm...
# [INFO]: Compiling to Wasm...
#  INFO 2019-09-09T16:55:21Z: wasm_pack::child: Running "cargo" "build" "--lib" "--target" "wasm32-unknown-unknown"
# [2019-09-09T16:55:21Z INFO  cargo::util::rustc] failed to read rustc info cache: failed to read `/markdown_img_url_editor/markdown_img_url_editor_rust/target/.rustc_info.json`
# [2019-09-09T16:55:21Z INFO  cargo::util::rustc] rustc info cache miss
# [2019-09-09T16:55:21Z INFO  cargo::util::rustc] rustc info cache miss
# [2019-09-09T16:55:21Z INFO  cargo::util::rustc] rustc info cache miss
# [2019-09-09T16:55:21Z INFO  cargo::util::rustc] rustc info cache miss
# [2019-09-09T16:55:21Z WARN  cargo::util::rustc] failed to update rustc info cache: failed to write `/markdown_img_url_editor/markdown_img_url_editor_rust/target/.rustc_info.json`
# error: failed to run `rustc` to learn about target-specific information

# Caused by:
#   process didn't exit successfully: `rustc - --crate-name ___ --print=file-names --target wasm32-unknown-unknown --crate-type bin --crate-type rlib --crate-type dylib --crate-type cdylib --crate-type staticlib --crate-type proc-macro` (exit code: 1)
# --- stderr
# error: Could not create LLVM TargetMachine for triple: wasm32-unknown-unknown: No available targets are compatible with triple "wasm32-unknown-unknown"
ENV PATH $PATH:/root/.cargo/bin
