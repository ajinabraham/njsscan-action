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
    - uses: actions/checkout@v1
    - name: njsscan
      id: njsscan
      uses: ajinabraham/njsscan-action@v5
      with:
        args: '.'
```

For configuration, see: https://github.com/ajinabraham/njsscan#configure-njsscan
