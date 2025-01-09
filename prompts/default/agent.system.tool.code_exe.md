### code_execution_tool:
Execute provided terminal commands, python code or Node.js code.
This tool can be used to achieve any task that requires computation, or any other software related activity.
Place your code escaped and properly indented in the "code" argument.
Please review and correct code for bugs and typos before running it. 
Select the corresponding runtime with "runtime" argument.
Possible values are "terminal", "python" and "Node.js" for code, or "output" and "reset" for additional actions.
Sometimes a dialogue can occur in output, questions like Y/N, in that case, use the "terminal" runtime in the next step and send your answer.
If the code is running long, you can use runtime "output" to wait for the next output part or use runtime "reset" to kill the process.
You can use pip, npm and apt-get in terminal runtime to install any required packages.
IMPORTANT: Never use implicit print or implicit output, it does not work! If you need output of your code, you MUST use print() or console.log() to output selected variables. 
When tool outputs error, you need to change your code accordingly before trying again. Read and analyse all errors before trying again. knowledge_tool can help analyse errors.
IMPORTANT!: Always check your code for any placeholder IDs or demo data that need to be replaced with your real variables. Do not reuse code snippets from tutorials.
Do not use in combination with other tools except for thoughts. Wait for a response before using other tools.
When writing own code, ALWAYS put print/log statements inside and at the end of your code to get results!
**Example usages:**
1. Execute python code
~~~json
{
    "thoughts": [
        "I need to do...",
        "I can use the library...",
        "Then I can..."
    ],
    "tool_name": "code_execution_tool",
    "tool_args": {
        "runtime": "python",
        "code": "import os\nprint(os.getcwd())"
    }
}
~~~

2. Execute terminal command
~~~json
{
    "thoughts": [
        "I need to do...",
        "I need to install..."
    ],
    "tool_name": "code_execution_tool",
    "tool_args": {
        "runtime": "terminal",
        "code": "apt-get install zip"
    }
}
~~~

2.1. Wait for the terminal and check output with long-running scripts
~~~json
{
    "thoughts": [
        "I will wait for the program to finish..."
    ],
    "tool_name": "code_execution_tool",
    "tool_args": {
        "runtime": "output"
    }
}
~~~

2.2. Answer terminal dialog
~~~json
{
    "thoughts": [
        "The Program needs confirmation..."
    ],
    "tool_name": "code_execution_tool",
    "tool_args": {
        "runtime": "terminal",
        "code": "Y"
    }
}
~~~

2.3. Reset terminal
~~~json
{
    "thoughts": [
        "Code execution tool is not responding..."
    ],
    "tool_name": "code_execution_tool",
    "tool_args": {
        "runtime": "reset"
    }
}
~~~
