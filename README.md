# Conda recipes

## Create a new recipe for a pure Python package on PyPI

1. Install conda-build and anaconda to your base Conda env:
   ```
   conda install conda-build anaconda 
   ```
2. Use [Grayskull](https://www.marcelotrevisani.com/grayskull) to create a new recipe file and fine-tune it.
3. Build the recipe:
   ```
   conda build <package>
   ```
4. Upload to Anaconda Cloud
   ```
   anaconda upload <path_to_created_package>
   ```

**Resources**

- [Building conda packages with conda skeleton](https://conda.io/projects/conda-build/en/latest/user-guide/tutorials/build-pkgs-skeleton.html)