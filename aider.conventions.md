 # Coding Standards
Unless otherwise specified, follow PEP8 guidelines for Python code formatting.

## Naming
- `snake_case` for variables and functions.
- `UPPER_CASE` for constants.

## Imports
- Order in three groups: standard library, third-party, local modules.
- Avoid wildcard imports (`from x import *`).

## Code Layout
- Limit lines to 79 characters.
- Separate logical sections with one blank line.
- Keep each file focused on a single responsibility.
- Where feasible, keep code concise, for example using list comprehensions.

## Functions & Classes
- Use `PascalCase` capitalization for classes.
- Keep them short and focused.
- Use descriptive parameter names.
- Include type hints in function signatures.
- Type annotations must be provided for all function inputs and return values (e.g., def foo(thing: str) -> str:).

## Docstrings
- Include detailed docstrings in Sphinx-like format for all functions and classes.
- Summarizing their purpose, inputs, return values, exceptions raised or side effects.
- Use triple double quotes (`"""Docstring"""`).
- Describe the parameters types and expected values examples.

## Testing
- Ensure each new function is accompanied by at least three unit tests using the pytest library: one positive ("happy path") test case and two negative (error-handling) test cases.
- Use clear, descriptive test names.
- Target essential paths first, then edge cases.
- Use fixtures for data where relevant, if you don't know the format create a placeholder and request the user fill it out.
- If using AWS boto libraries, use `moto` library to test.

## Executing commands
- Always execute python code as such: "python example.py". Do not mark them as +x executables.

## Security
- Never hardcode secrets or credentials into the code, use .env files.
- Ensure .env files are in .gitignore.
- Install and run the bandit tool to assess whether there are security issues.

## Libraries
- Run the pip install first when adding a new library to see the latest version.
- Update requirements.txt whenever adding or removing libraries. When adding, use the latest version.
- Add libraries required only for testing purposes (e.g., pytest) to dev-requirements.txt instead.
