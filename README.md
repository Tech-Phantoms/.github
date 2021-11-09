<div align="center">
<img src="https://github.com/Tech-Phantoms/community/blob/main/assets/banner.png?raw=" width="80%" />

<h1 />
</div>

> This repo is meant for Tech Phantoms config files. 

<br>


### Use the labels we use for issue tracking 
Check our label config file [here](https://github.com/Tech-Phantoms/.github/blob/main/.github/label-list.yml)

**use this gh action** 
```yaml

name: Sync labels
on:
  # You can run this with every type of event, but it's better to run it only when you actually need it.
  workflow_dispatch:

jobs:
  labels:
    runs-on: ubuntu-latest

    steps:
      - uses: EndBug/label-sync@v2
        with:
          # If you want to use a config file, you can put its path or URL here (more info in the paragraphs below)
          config-file: 'https://github.com/Tech-Phantoms/.github/blob/main/.github/label-list.yml'

          # If you want to delete any additional label, set this to true
          delete-other-labels: false

            # You can change the token used to change the labels, this is the default one
          token: ${{ secrets.GITHUB_TOKEN }}
```