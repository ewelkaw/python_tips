## **GOOD CODE REVIEW RULES** ##
### **1. Definition of done**
    
1. You need to know what kind of problem you want to solve and what are the principles of accepting solution.

2. What are the company standards that should be used in projects, are some of them covered by continuous integration

### **2. Stages of review**
1. Before PR submission:
	- What was the motivation for submitting this code? 
    - Link to the underlying ticket/issue 	
    - Document why the change was needed 	
    - For larger PRs, provide a changelog 
    - Point out any side-effects 
2. PR to be submitted:
    - Did you check for reusable code or utility methods? 
    - Did I remove debugger statements? 
    - Are there clear commit messages? 
    - Is my code secure? 
    - Will it scale?		
    - Is it maintainable? 
    - Is it resilient against outages? 
3. (optional) Work in progress PR (30-50%): 
    - Open them your code is 30-50% done 
    - Good idea for bigger features 
    - Don’t be afraid of showing incomplete, incremental work 
    - Feedback to expect: 
        -Architectural issues 
        -Problems with overall design 
        -Design pattern suggestions 
4. Review almost done (90-100%): 
    - Feedback to expect:	
        - Nit Picks		
        - Variable Names 
        - Documentation & Comments 
        - Small Optimizations (if you hear that you need to change it all then you have some bigger problem with communication)
5. Review completed. 

### **3. Tips & Tools**

1. TIPS:
    - Solving multiple problems? Break them up into multiple PRs for ease of review. 
    - Solved an unrelated problem? Make a new PR with a separate diff 
    - Reviews lose value when they’re more than 500 lines of code
    - Keep them small & relevant 
    - If a big PR is unavoidable, give the reviewer extra time 
    - Pre-commit hooks:
        - run linter
        - check syntax
        - check for TODOs, debugger statements, unused imports
        - enforce styling (autopep8, black formatter, sort imports, etc)
        - option to reject commit if conditions don't pass
2. TOOLS:
    1. linter: pylint
        - Coding standard		
        - Error detection		
        - Refactoring help		
        - IDE & editor integration 
	2. vulture - to find dead or unreachable code
    ```bash
    pip install vulture
    vulture script.py package/
    ```
    or
    ```
    python -m vulture script.py package/
    ```
    3. formatters: black, YAPF, autopep8
    4. pre-commit - framework for managing and maintaining multi-language pre-commit hooks
        - autopep8-wrapper - Runs autopep8 over source
        - flake8 and pyflakes - Run flake8 or pyflakes on source
        - check-ast - Check whether files contain valid python
        - debug-statements - Check for debugger imports and breakpoint() calls
    5. continuous integration
    6. coverage - % of code executed when runnint a test suite
    7. VS Code life share
    8. Nit-picking
        - Syntax Issues
        - Spelling Errors
        - Poor Variable Names
        - Missing corner-cases
        - Specify: Are your nitpicks blocking merge?
        Save the nit-picks for last, after any pressing
        architecture, design, or other large scale issues have been addressed.