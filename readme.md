# Air JSON Schema Generator

This is a tool that generates a JSON schema for Air configuration files (`.air.toml`) based on the source code of Air. 
The generated schema can be used with the [Even Better Toml](https://marketplace.visualstudio.com/items?itemName=tamasfe.even-better-toml) VS Code extension for schema-based validation and autocompletion.

# Usage

## Generate the schema

Clone the repository, change to the repository directory and run the program:

    git clone https://github.com/romamik/go-air-schema-gen
    cd go-air-schema-gen
    go run .

This will generate the schema in the current directory.

## Add the schema to VS Code

Add the following to your VS Code settings:
```json
    "evenBetterToml.schema.associations": {
        ".*/.air.toml": "file:///full/path/to/air-schema.json"
    }
```
Make sure to replace `"file:///full/path/to/air-schema.json"` with the correct file path where the generated `"air-schema.json"` is located.

> **Side Note**: There is a slight problem as `".*/.air.toml"` is a regex, so dots match any character and not only dots, as it is intended, but I failed to find a way around this.
