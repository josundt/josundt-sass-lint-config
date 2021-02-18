# @josundt/sass-lint-config #

> Ruleset for sass (scss) code style and linting

## Usage ##
1. Install this package 

2. Add the following to your **package.json** file: 
    ```json
    {
      "sasslintConfig": "node_modules/@josundt/sass-lint-config/.sasslintrc"
    }
    ``` 

3. Add npm task in **package.json**
    ```json
    {
      "scripts": {
        "lint:sass": "sass-lint src/**/*.scss --format visualstudio -v"
    },
    }
    ```

4. When using Visual Studio Code:  

    __a)__ Install the sass-lint extension (_"glen-84.sass-lint"_), and add it
       to the recommmended extensions for the workspace (_".vscode/extensions.json"_).

    __b)__ Add a task in _".vscode/tasks.json"_ to run sass-lint as a VSCode task for the
       whole workspace:
    ```json
    {
      "version": "2.0.0",
      "runner": "terminal",
      "tasks": [
        {
          "label": "lint:sass",
          "type": "shell",
          "command": "npx",
          "args": [
            "sass-lint",
            "src/**/*.scss",
            "--format",
            "stylish",
            "-v"
          ],
          "group": "build",
          "presentation": {
            "echo": true,
            "reveal": "silent",
            "focus": false,
            "panel": "shared"
          },
          "problemMatcher": {
            "base": "$eslint-stylish",
            "fileLocation": [
              "relative",
              "${workspaceRoot}"
            ],
            "source": "lint:sass"
          }
        }
      ]
    }
    ```
