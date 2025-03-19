Experimant - 8
Write shell scripts to print system information.
Write shell script to perform basic mathematical calculation.
Use redirection operators to store the output of commands.

Approach: 
System Info Script → redirectionOperator.sh collects system details and saves them in redirectionOperatorsResult.txt using redirection.
Calculator Script → calculator.sh performs basic math operations based on user input.
Redirection Usage → Scripts store outputs in files (> for overwrite, >> for append) and comment outputs using sed. 

Implementation:
System Info Script

code:

#!/bin/bash

echo "================================="
echo "      System Information         "
echo "================================="
lscpu

![image](https://github.com/user-attachments/assets/5102e39f-faa6-4093-8c5b-8c6608551be1)


Implementation:
Calculator Script

code :

#!/bin/bash

echo "Enter the operation (+, -, *, /): "
read operation
echo "Enter first number: "
read no1
echo "Enter second number: "
read no2

case $operation in
"+") echo "Result: $((no1 + no2))" ;;
"-") echo "Result: $((no1 - no2))" ;;
"*") echo "Result: $((no1 * no2))" ;;
"/") 
 if [ "$no2" -ne 0 ]; then
          echo "Result: $((no1 / no2))"
      else
          echo "Error: Division by zero is not allowed."
      fi
      ;;
  *) echo "Invalid operation!" ;;
esac

![image](https://github.com/user-attachments/assets/cb350a94-c411-4d84-b96b-6380013f78c7)


Implementation:
Redirection Usage

code :

!/bin/bash

echo "Enter command to store:"
read -a command  

"${command[@]}" >> redirectionOperatorsResult.txt 2>&1

echo "Output stored in redirectionOperatorsResult.txt"

![image](https://github.com/user-attachments/assets/72653cbd-e45d-4ab9-89ab-18ec02e4f4d1)







