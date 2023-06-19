# openapi-sync-action

GitHub action for downloading and syncing a remote `openapi.yaml` file

## Usage

Simply provide a URL for the remote OpenAPI specification file. If an `openapi.yaml` file already exists in the repository, the action will download it again from said URL and compare both files. If they differ, the latest one will become `openapi.yaml`. Otherwise, nothing changes.

Here's an example of how you could use it in your job:

```yaml
on: [push]

jobs:
  my_job:
    runs-on: ubuntu-latest
    name: Lorem ipsum dolor
    steps:
      - uses: actions/checkout@v3

      - uses: maximiliancw/openapi-sync-action@latest
        with:
          # Enter the URL of the remote OpenAPI spec
          openapi-url: https://example.com/api/v1/openapi.yaml

      # Commit all changed files back to the repository
      - uses: stefanzweifel/git-auto-commit-action@v4

```

## License 
MIT License

Copyright (c) 2023 Maximilian Wolf

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.