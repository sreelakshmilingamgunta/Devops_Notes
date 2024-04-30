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
```
>> poetry run my_name_script
```
