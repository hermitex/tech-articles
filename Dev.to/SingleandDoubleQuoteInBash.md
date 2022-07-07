# Differences between Single and Double Quotes in Bash

Although for the most part they behave almost exactly the same, single quotes ('') and double quotes ("") are fundementally different in Bash.

## How different are they?

Well, assume we have the a script hello-world.sh which takes in one positional argument and prints a message to the terminal:

```bash
#!/bin/bash
echo "Hello, $1" # using double quotes
```

Output

```
hello-world.sh Tiberius
# => Hello Tiberius
```

That executes and gives us the expected output. Great!

Now let us have a look at what happens when we instead use single quotes with the same script:

```bash
#!/bin/bash
echo 'Hello, $1' #using single quotes
```

Output

```
hello-world.sh Tiberius
# => Hello $1
```

Well, from the second output script above, we see that the result is not what we expected.

## What happened?

When using single double quotes, bash will protect all the characters eclosed in the double quotes. That is to say, bash will read them all without giving them any special treatment or meaning. However, when it encounters `$` it will expand the double quotes to and replace it with the meaning it carries. In our example, this evaluates to the name passed to bash when executing the script.

On the other hand, the single quotes protect everything enclosed in double quotes including the `$`. Therefore, when executing the script, bash does not expand the `$` to give it te meaning it carries. Rather, it simply prints it out in its literal form. That is why the arguement for second script did not evaluate to the value passed.

## What if I want to use the `$` symbol?

If at all we wish to use the `$` symbol, we will have to instruct bash to escape it where appropriate.

Here is an example:

```bash
#!/bin/bash
echo "Hello, $1! Today you earned \$2" #using $ as a symbol
```

Output

```
hello-world.sh Tiberius
# => Hello Tiberius! Today you earned $2
```

## Key Takeaways

- In bash, single quotes and double quotes behabve almost the same but they have diffent behaviors in certain cases.
- If you want to evaluate the value of a variable in a string, use a double quotes.
- Double quotes allows bash to exapand the varibale name and replace it with the actual value.
- Using single quotes will not allow bash to evaluate the value of a variable. Rather than, it prints the variable name.
