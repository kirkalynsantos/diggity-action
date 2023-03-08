
# diggity-action
diggity provides organizations with a more comprehensive look at their application to take calculated actions and create a better security approach. Its primary purpose is to scan vulnerabilities to implement subsequent risk mitigation measures. 

## Directory Scanning

```yaml
name: Diggity Action
on: [push, pull_request]
jobs:
  diggity:
    runs-on: ${{matrix.os}}
    strategy:
      matrix:
        os: [ubuntu-latest] # can add more os: windows-latest, macOS-latest
    steps:
      - name: Run carbonetes/diggity # runs the github action of diggity
        uses: carbonetes/diggity@v1.0.0 # runs the github action using this version
        with: # user’s input reference for scanning options, results that diggity-action supported.
          fail_on_vulnerability: true # sample output reference: job fails when vulnerability found.
          path: "."

```

## License

[Apache 2.0](https://choosealicense.com/licenses/apache-2.0/)
