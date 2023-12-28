Shell variables and expansions

## Converting a Number from Base 10 to Base 16
There are several ways of converting a number from base 10 to base 16. 
Below are three ways of performing the base conversion:

### 1. Using the printf command
Below is the syntax you can use to perform the base conversion:

	printf "%x\n" "$DECIMAL"

where $DECIMAL is the environment variable used for storing the value to be converted.

Let's try an example of converting the number 1337:

	printf "%x\n" 1337

The script will return the value 539.

### 2. Using the `bc` (arbitrary precision calculator)
In this case, the `bc` command-line calculator sets the input base (`ibase`) to 10, and the output base (`obase`) to 16, which then performs the conversion.

An example is as shown below:

	echo "ibase=10; obase=16; $DECIMAL" | bc

Replace the $DECIMAL variable with a value for conversion. Say 15.

	echo "ibase=10; obase=16; 15" | bc

The script will print `F` as the output. 

You can also shorten the syntax this way:

	echo 'obase=10;16' $DECIMAL | bc

It will still produce the same outcome. 
