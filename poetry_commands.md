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



```
**Available commands:**    
  about              Shows information about Poetry.  
  add                Adds a new dependency to pyproject.toml.  
  build              Builds a package, as a tarball and a wheel by default.  
  check              Validates the content of the pyproject.toml file and its consistency with the poetry.lock file.  
  config             Manages configuration settings.  
  export             Exports the lock file to alternative formats.  
  help               Displays help for a command.  
  init               Creates a basic pyproject.toml file in the current directory.  
  install            Installs the project dependencies.  
  list               Lists commands.  
  lock               Locks the project dependencies.  
  new                Creates a new Python project at <path>.  
  publish            Publishes a package to a remote repository.  
  remove             Removes a package from the project dependencies.  
  run                Runs a command in the appropriate environment.  
  search             Searches for packages on remote repositories.  
  shell              Spawns a shell within the virtual environment.  
  show               Shows information about packages.  
  update             Update the dependencies as according to the pyproject.toml file.  
  version            Shows the version of the project or bumps it when a valid bump rule is provided.  
  
 **cache**    
  cache clear        Clears a Poetry cache by name.  
  cache list         List Poetry's caches.  

 **debug**    
  debug info         Shows debug information.  
  debug resolve      Debugs dependency resolution.  

 **env**    
  env info           Displays information about the current environment.  
  env list           Lists all virtualenvs associated with the current project.  
  env remove         Remove virtual environments associated with the project.  
  env use            Activates or creates a new virtualenv for the current project.  

 **self**    
  self add           Add additional packages to Poetry's runtime environment.  
  self install       Install locked packages (incl. addons) required by this Poetry installation.  
  self lock          Lock the Poetry installation's system requirements.  
  self remove        Remove additional packages from Poetry's runtime environment.  
  self show          Show packages from Poetry's runtime environment.  
  self show plugins  Shows information about the currently installed plugins.  
  self update        Updates Poetry to the latest version.  

 **source**    
  source add         Add source configuration for project.  
  source remove      Remove source configured for the project.  
  source show        Show information about sources configured for the project.  
```


