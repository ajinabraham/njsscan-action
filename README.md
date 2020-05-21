# njsscan Action
njsscan finds insecure code patterns in your node.js applications.

## Example Usage

Add the following file at `.github/workflows/njsscan.yml`:

```yaml
name: njsscan
on: [pull_request]
jobs:
  njsscan:
    runs-on: ubuntu-latest
    name: njsscan check
    steps:
    - uses: actions/checkout@v1
    - name: njsscan
      id: njsscan
      uses: ajinabraham/njsscan-action@v1
```
