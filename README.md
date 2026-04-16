# wasco.dev

Website and WebAssembly package registry reference for [wasco.dev](https://wasco.dev).

# Getting WASM files
## Installing tooling
To get the WASM file for a specific component you need the wash CLI. This is a tool to interact with the wasmCloud stack and also fetch our WASM file.
 You can install this tool in your CLI with:
```Bash
cargo install wash
```
if you have [Cargo](https://doc.rust-lang.org/cargo/getting-started/installation.html) installed.
It is important to note that there is also an older version of the wash CLI that is no longer supported called `wash-cli`. If this is installed then please remove it and install the correct version as the above describes.

After having installed the wash CLI you should be able to run:
```Bash
wash --version
```
And see something like:
```
wash          v0.43.0
├ nats-server v2.11.3
├ wadm        v0.21.1
└ wasmcloud   v1.9.1
```
Don't worr if you see warnings or extra information.

## Using tooling
Now that we have the wash CLI we can get the WASM file for our component. Simply go to the GitHub page for the component you want to download like https://github.com/wasco-dev/glyphic-api and look at the right-hand side and look for the text "packages".
![[assets/repo-packages.png]]
You should be able to click on the "packages" text and it will redirect you to a page with all the available components, this is usually one per page.
![[assets/packages.png]]
If the "packages" says "No packages published" below it, then please request the component author to upload their component to the GitHub package registry.
Here you can click again on the specific component you want the WASM file for and you'll be brought to a page where you can see all the versions of a component and an example on how to "pull" it. The way of pulling the component that is presented will not give you a WASM file, instead do:
```Bash
wash pull ghcr.io/wasco-dev/glyphic-api:1.0.0
```
This will give you your WASM component in the place the terminal is opened. Please navigate to the place your terminal is in your file explorer to find the WASM file.
(Tip: You can run pwd to see where your terminal is opened to quickly find the WASM file.)
You should see you WASM component named as glyphic-api.wasm for this example
