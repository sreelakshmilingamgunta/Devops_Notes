- Python Poetry is a tool used for managing dependencies in Python projects
- Poetry helps you keep track of which tools you need and makes sure you have the right versions.
- Instead of manually keeping track of dependencies and versions in text files, Poetry streamlines the process. It uses a single file (pyproject.toml) where you list all your project's dependencies and their versions.  
- Poetry creates isolated environments for your projects, meaning each project can have its own set of tools (dependencies) without interfering with other projects. It's like having separate workbenches for different projects.
- **Lock File:** When you run poetry install, Poetry generates a lock file (poetry.lock) alongside the pyproject.toml file. This lock file records the exact versions of all dependencies and their transitive dependencies, ensuring reproducible builds. It's like a snapshot of your project's dependencies at a specific point in time.
- Integration with Package Indexes: Poetry integrates seamlessly with popular Python package indexes like PyPI (Python Package Index) and allows you to specify dependencies from other sources as well. You can also specify dependencies directly from Git repositories or local file paths.

```
# creating new project  
poetry new new-project  
it will create a project and folder with new-project name if we want to specify different names for project and folders
poetry new My-project --name My-folder
```
If you want to add dependencies to your project, you can specify them in the [tool.poetry.dependencies] section in pyproject.toml  
`
poetry install`  
or   
use 'add' command  to add dependencies  
`poetry add <package Name> `





**How Run Scripts?**
```
# Name.py

def main():
    # Your script code goes here
    print("Hello, world!")

if __name__ == "__main__":
    main()
```
```
[tool.poetry.scripts]
my_name_script = "Name:main"
```
`>> poetry run my_name_script
`
