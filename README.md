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
4. Upload to Anaconda Cloud
   ```
   anaconda upload <path_to_created_package>
   ```
   Want to upload to an organisation you're a member of? Use the
   [`--user` flag](https://docs.anaconda.com/anacondaorg/user-guide/tasks/work-with-organizations/#uploading-packages-to-an-organization).

**Resources**

- [Building conda packages with conda skeleton](https://conda.io/projects/conda-build/en/latest/user-guide/tutorials/build-pkgs-skeleton.html)
- [Working with packages](https://docs.anaconda.com/anacondaorg/user-guide/tasks/work-with-packages/)
