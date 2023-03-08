
# diggity-action
BOM Diggity’s primary purpose is to ensure the security and integrity of software programs. It incorporates secret analysis allowing the user to secure crucial information before deploying any parts of the application to the public.

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
          path: "."

```

## License

[Apache 2.0](https://choosealicense.com/licenses/apache-2.0/)
