# Conda recipes

## Create a new recipe for a pure Python package on PyPI

1. Install conda-build and anaconda to your base Conda env:
   ```
   conda install conda-build anaconda-client
   ```
2. Use [Grayskull](https://www.marcelotrevisani.com/grayskull) to create a new recipe file and fine-tune it.
3. Build the recipe:
   ```
   conda build <package>
   ```
   You might have to add extra channels to this command to correctly resolve dependencies.
   Example:
   ```
   conda build -c conda-forge <package>
   ```
   You can also use Mamba as your env solver for improved build performance (install [Boa](https://github.com/mamba-org/boa) first):
   ```
   conda mambabuild <package>
   ```
4. Upload to Anaconda Cloud
   ```
   anaconda upload <path_to_created_package>
   ```
   Want to upload to an organisation you're a member of? Use the
   [`--user` flag](https://docs.anaconda.com/anacondaorg/user-guide/tasks/work-with-organizations/#uploading-packages-to-an-organization).

## Troubleshooting: Upload fails silently

While uploading, check the error code carefully. If the upload step finishes and returns a code different from 0 (`echo $?` will show the exit code), something went wrong and the upload did not succeed. This is a long-discussed issue (*e.g.* https://github.com/Anaconda-Platform/anaconda-client/issues/501) and this silent failure can have several reasons.

I had trouble using anaconda-client 1.7.2 with Python 3.9.4. Using Python 3.7 fixed the issue.

## Troubleshooting: ModuleNotFoundError: No module named 'poetry'

If this happens, try and add `poetry` to your recipe's `requirements.host` section.

**Resources**

- [Building conda packages with conda skeleton](https://conda.io/projects/conda-build/en/latest/user-guide/tutorials/build-pkgs-skeleton.html)
- [Working with packages](https://docs.anaconda.com/anacondaorg/user-guide/tasks/work-with-packages/)
