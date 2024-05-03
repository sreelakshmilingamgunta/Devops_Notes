```
*Installation steps for Ubuntu:
sudo apt update && sudo apt install python3
python3 --version
sudo apt install python3-pip
pip install poetry
vi ~/.bashrc
export PATH="$HOME/.local/bin:$PATH"
source ~/.bashrc
poetry --version

```
```
>> poetry about --> displays global information about Poetry
>> poetry list --> displays all the available poetry commands
*creating new project
  >> poetry new
  >> poetry new <My-folder-name> --name <My-projct -name>
  >> poetry init --> if we want to initialize project in existing folder
>> poetry version
*Installing dependencies
  >> poetry install --> reads the pyproject.toml file from the current project, resolves the dependencies, and installs them.  
  >> poetry install --without <group_name> --> If you want to exclude one or more dependency groups for the installation.  
  >> poetry install --with <group_name> --> You can also select optional dependency groups with the --with option.  
  >> poetry install --only <group_name> --> To install only specific from specific group.  
  >> poetry install --sync --> To synchronize your environment – and ensure it matches the lock file.  
>> poetry update --> Inorder to get the latest versions.  
>> poetry add <package_name> --> adds required packages.
>> poetry add <package_name> --group <group_name> --> to add packages to specific group
>> poetry remove <package_name> --> removes packages from installed packages.  
>> poetry remove <package_name> --group <geoup_name> --> removes packages from different groups.  
>> poetry show --> to list all the available packages.  
>> poetry show <package> --> to see information about specific package.  
>> poetry build --> to package your project for distribution.  
>> poetry publish --> after running poetry build to publish your package to a package repository.
>> poetry run python -V --> executes the given command inside the project’s virtualenv.  

if you define script in the pyproject.toml file
[tool.poetry.scripts]
my-script = "my_module:main"

>> poetry run my-script

>> poetry list --> displays all the available Poetry commands.
>> poetry cache list -->  lists Poetry’s available caches.
>> poetry cache clear pypi --all -->  to clear the whole cache of packages from the pypi repository

>> poetry self add poetry-plugin-export --> works exactly like the add command. However, is different in that the packages managed are for Poetry’s runtime environment.
>> poetry self update --> works exactly like the update command. However, is different in that the packages managed are for Poetry’s runtime environment.
>> poetry self show --<options> -->To show only additional packages that have been added via self add and their dependencies use

*Managing environments
>> poetry env use /full/path/to/python
>> poetry env use python3.7 --> If you have the python executable in your PATH you can use it:
>> poetry env use system
>> poetry env info --> If you want to get basic information about the currently activated virtual environment
>> poetry env info --path --> If you only want to know the path to the virtual environment.
>> poetry env list --> listing the environments associated to project
>> poetry env remove /full/path/to/python --> to delete the existing environment
>> poetry env remove --all --> to delete all the virtual environements once  ```


