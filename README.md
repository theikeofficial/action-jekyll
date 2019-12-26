<!-- [![Docker Automated build](https://img.shields.io/docker/cloud/build/faph/action-jekyll)](https://cloud.docker.com/repository/docker/faph/action-jekyll/) -->

# A GitHub Action for just building Jekyll web sites

We're only building the site here. If you want to do some other stuff with those
site files like deploying them, or running some build scripts on them — you'll 
have to connect up some other actions to your workflow.

## Inputs

- `destination_dir`: Optional. Jekyll destination directory. Default: `_site`, 
  directory within the checked out repository.
- `add_nojekyll_tag`: Optional. Whether to add a .nojekyll file to the 
  destination directory to prevent GitHub building the website with Jekyll. 
  Default: `true`.

## Examples

```yaml
jobs:
  build:
    name: Build website
    runs-on: ubuntu-latest
    steps:

    - name: Checkout repository
      uses: actions/checkout@v1
      with:
        ref: master
    
    - name: Run Jekyll
      uses: theikeofficial/action-jekyll@master
```

Clones the repo and builds the site — that's it.

## Caveats

* Needs a Gemfile in the working directory.
* Be sure that any custom gems needed are included in your Gemfile.

## Terms & Conditions

Released under the [MIT License (MIT)](LICENSE).

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR 
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS
FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR 
COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER 
IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN 
CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
