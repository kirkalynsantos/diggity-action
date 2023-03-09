<p align="center">
<img src="assets/diggity-black.png" style="display: block; margin-left: auto; margin-right: auto; width: 50%;">
</p>

# Diggity Github Action
A Github Action integrated with [Diggity](https://github.com/carbonetes/diggity#readme) to generate software bill-of-materials (SBOM).
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
          directory: "." # path to directory to be scanned
          output_type: json # desired output format (default table)

```

## License

[Apache 2.0](https://choosealicense.com/licenses/apache-2.0/)