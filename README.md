# E2E-Test-Dapp
   This is a simple test dapp for use in MetaMask e2e tests and manual QA.

## Usage
  If you wish to use this dapp in your e2e tests, install this package and set up a script of e.g. the following form:
  
```shell
   static-server node_modules/@metamask/test-dapp/dist --port 9011
```

## Development
![2023-02-08 (1)](https://user-images.githubusercontent.com/91811381/217407430-ec182b07-234e-4b84-b07d-0e22df2f7bc5.png)

### Requires Manual Deployment

    After merging or pushing to `master`, please run `yarn deploy` in the package root directory if the contents of the `dist/` directory have changed.


### Elements Must Be Selectable by XPath

  Consider that elements must be selectable by XPath. This means that appearances can be misleading.
  For example, consider this old bug:
  
 ```html
       <button class="btn btn-primary btn-lg btn-block mb-3" id="approveTokensWithoutGas" disabled>
          Approve Tokens
           Without Gas
       </button>
```


This appears on the page as `Approve Tokens Without Gas`. In reality, the value included the whitespace on the second line, and caused XPath queries for the intended value to fail:

```html
Approve Tokens 
Without Gas
```
