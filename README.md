
# HOWTOUSE.md - Help File Generator for Python Scripts

**Never write another \*.md file for Python again!**  
Let your docstrings do the work while this tool handles the documentation.

## Features That Will Make You Smile 😊

✨ **Set It and Forget It** - Initialize once and your help files stay magically updated  
🔍 **Smart Difference Checking** - Only updates what's changed (no more pointless rewrites)  
📚 **Comprehensive Documentation** - Extracts everything from docstrings to type hints  
🧭 **Built-in Navigation** - Automatic table of contents with quick links to all sections  
⚡ **Usage Examples** - Generates sample code snippets showing how to call each function  
🎯 **Exclusion Support** - Skip private/internal methods with a simple JSON config  

## Installation

Just drop this script in your project! No dependencies needed (except Python 3.6+).

## Basic Usage

```python
from help_generator import HelpFileGen

# For a single script
help_gen = HelpFileGen("your_script.py")

# For a package (will process all __init__.py files)
help_gen = HelpFileGen("your_package/")
```

That's it! Your `your-script-help.md` file will be automatically created/updated.

## Advanced Options

```python
HelpFileGen(
    module_path="your_module.py",
    output_file="CUSTOM_NAME.md",  # Default: "help.md"
    overwrite=False,               # Default: True (safe mode)
    include_args=True             # Show arguments in separate section
)
```

## How It Works - The Magic Behind the Scenes

1. **AST Walking** - Parses your Python files without executing them
2. **Docstring Extraction** - Pulls help text from all your carefully written docstrings
3. **Signature Analysis** - Shows argument types, defaults, and kwarg details
4. **Checksum Comparison** - Only updates what's changed since last run
5. **Markdown Generation** - Creates beautiful, navigable documentation

## Example Output Structure

```markdown
# Table of Contents
[Classes] | [Functions]

## Class: `MyAwesomeClass`
[Method 1] | [Method 2] | [Method 3]

### Method: `do_something`
#### Arguments:
- param1: str = "default"
- param2: int

#### Help:
> This method does something amazing with the parameters...

#### Usage:
```python
obj = MyAwesomeClass()
obj.do_something(
    "custom_value",
    42
)

[Back to MyAwesomeClass] | [Back to Top]
```

## Pro Tips

1. **Exclusion List** - Add private methods to `.jsondata/exclude_help_ast.json`
2. **Checksum Tracking** - Stored in `.jsondata/*.checksums.json` for smart updates
3. **Type Hint Love** - The more type hints you add, the better your docs will be!

## Coming Soon to a Terminal Near You...

🌐 **Multi-language Support** (JavaScript, Ruby, and more on the roadmap)  
🔗 **Cross-reference Linking** between related functions  
📊 **Visualization Generation** for complex class hierarchies  

## Final Thought

Why waste time writing documentation that goes stale immediately? Let your code document itself - the way it should be!

**Never write another \*.md file for Python again!** 🎉

