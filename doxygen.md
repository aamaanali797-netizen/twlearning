# Doxygen

Doxygen is a tool that generates documentation from source code comments. It works with C, C++, Python, Java and other languages. You write special comments in your code and Doxygen creates HTML or PDF documentation from them.

## Why Use Doxygen

- Keeps documentation close to the code
- Automatically generates cross-references between functions and classes
- Creates call graphs and inheritance diagrams
- Output in HTML, LaTeX, or PDF
- Widely used in industry for API documentation

## Installation

- Windows: download from https://www.doxygen.nl/download.html
- Linux: `sudo apt-get install doxygen`
- Mac: `brew install doxygen`

Check with: `doxygen --version`

## Basic Workflow

1. Write special comments in your source code
2. Generate a config file: `doxygen -g Doxyfile`
3. Edit the Doxyfile if needed (project name etc)
4. Run: `doxygen Doxyfile`
5. Open `html/index.html` to see the output

## Comment Syntax (C/C++)

```cpp
/**
 * \brief Short description of the function.
 *
 * Detailed description goes here.
 * \param x Description of parameter x
 * \return What the function returns
 */
int myFunction(int x);
```

## Comment Syntax (Python)

```python
def foo(bar):
    """
    Brief description.

    More details here.
    :param bar: description of bar
    :type bar: int
    :return: what it returns
    :rtype: int
    """
    return bar + 1
```

## Documenting a Class

```cpp
/**
 * \class Car
 * \brief Represents a car object.
 *
 * Details about the class.
 */
class Car {
public:
    /**
     * \brief Start the engine
     * \return True if successful
     */
    bool startEngine();
};
```

## Common Doxygen Tags

| Tag | What it does |
|-----|-------------|
| `\brief` | Short summary |
| `\param` | Describe a parameter |
| `\return` | Describe return value |
| `\author` | Author info |
| `\version` | Version number |
| `\see` | Reference to related items |
| `\note` | Additional notes |
| `\class` | Document a class |

## Doxyfile Settings

Some important settings in the config file:
- `PROJECT_NAME` - name of your project
- `OUTPUT_DIRECTORY` - where docs get generated
- `INPUT` - source files/folders to scan
- `HAVE_DOT = YES` - enables graphviz diagrams
- `EXTRACT_ALL = YES` - document everything even without comments

## Diagrams

If you have Graphviz installed and set `HAVE_DOT = YES`, Doxygen can generate:
- Class inheritance diagrams
- Call graphs (which functions call what)
- Collaboration diagrams

## When to Use Doxygen

- When you need to document a codebase (library or API)
- When documentation should stay in sync with code
- When you want auto-generated reference manuals
- For open-source projects where contributors need API docs
