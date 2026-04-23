# wasco.dev

Website and WebAssembly package registry reference for [wasco.dev](https://wasco.dev).

# Getting WASM files
## Installing tooling
To get the WASM file for a specific component you need the wash CLI. This is a tool to interact with the wasmCloud stack and also fetch our WASM file.
You can install this tool by following [these docs](https://wasmcloud.com/docs/installation/).
It is important to note that there are also older version of the wash CLI which are no longer supported. If `wash --version` does not give a version higher than `2.0.0` then it is an older version of the CLI. Please uninstall it before installing wash with the link above.

After having installed the wash CLI you should be able to run:
```Bash
wash --version
```
And see something like:
```
wash 2.0.4
```

## Using tooling
Now that we have the wash CLI we can get the WASM file for our component. Simply go to the GitHub page for the component you want to download like https://github.com/wasco-dev/glyphic-api and look at the right-hand side and look for the text "packages".
![alt text](https://github.com/wasco-dev/wasco-dev/raw/main/assets/repo-packages.png "GitHub repo")  

You should be able to click on the "packages" text and it will redirect you to a page with all the available components, this is usually one per page.
![alt text](https://github.com/wasco-dev/wasco-dev/raw/main/assets/packages.png "GitHub package registry")  

If the "packages" says "No packages published" below it, then please request the component author to upload their component to the GitHub package registry.
Here you can click again on the specific component you want the WASM file for and you'll be brought to a page where you can see all the versions of a component and an example on how to "pull" it. The way of pulling the component that is presented will not give you a WASM file, instead do:
```Bash
wash oci pull ghcr.io/wasco-dev/glyphic-api:0.1.0
```
Now you should see something like `Pulled and saved component to /home/$USER/component.wasm`. Beware that this will overwrite any existing `component.wasm` file you had in the directory of your terminal.
After pulling the file you can it in your file explorer in path the wash CLI gave.
