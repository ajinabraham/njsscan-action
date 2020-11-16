# njsscan action
njsscan finds insecure code patterns in your node.js applications.

## Example Usage

Add the following file .github/workflows/njsscan.yml to your node.js repositories in Github to enable njsscan in your CI/CD or DevSecOps pipeline.

```yaml
name: njsscan
on:
  push:
    branches: [ master ]
  pull_request:
    branches: [ master ]
jobs:
  njsscan:
    runs-on: ubuntu-latest
    name: njsscan check
    steps:
    - name: Checkout the code
      uses: actions/checkout@v2
    - name: nodejsscan scan
      id: njsscan
      uses: ajinabraham/njsscan-action@master
      with:
        args: '.'
```

### Github Code Scanning SARIF upload

```yaml
name: njsscan
on:
  push:
    branches: [ master ]
  pull_request:
    branches: [ master ]
jobs:
  njsscan:
    runs-on: ubuntu-latest
    name: njsscan code scanning
    steps:
    - name: Checkout the code
      uses: actions/checkout@v2
    - name: nodejsscan scan
      id: njsscan
      uses: ajinabraham/njsscan-action@master
      with:
        args: '. --sarif --output nodejsscan_results.sarif || true'
    - name: Upload njsscan report
      uses: github/codeql-action/upload-sarif@v1
      with:
        sarif_file: nodejsscan_results.sarif
```
For configuration, see: https://github.com/ajinabraham/njsscan#configure-njsscan
