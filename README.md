# python_calc_working
import re


def add(number):
    s = int(number[0])+int(number[1])
    number.append(number.pop(0))
    number.append(number.pop(0))
    return s


def subtract(number):
    s = int(number[0])-int(number[1])
    number.append(number.pop(0))
    number.append(number.pop(0))
    return s


def multiply(number):
    s = int(number[0])*int(number[1])
    number.append(number.pop(0))
    number.append(number.pop(0))
    return s


def divide(number):
    s = int(number[0])/int(number[1])
    number.append(number.pop(0))
    number.append(number.pop(0))
    return s


def main():
    calculation = input("Type your calculation")
    numbers = re.findall(r'\d+', calculation)
    print(numbers)
    ans = 0
    for x in calculation:
            if x == "+":
                ans = add(numbers)
                numbers[0] = ans
            elif x == "-":
                ans = subtract(numbers)
                numbers[0] = ans
            elif x == "*":
                ans = multiply(numbers)
                numbers[0] = ans
            elif x == "/":
                ans = divide(numbers)
                numbers[0] = ans
            else:
                    print("scanning...")
    print(ans)

i=1
while(i == 1):
    a= input("Do you want to calculate something?").lower()
    print(input)
    if a == "yes":
        main()
    else:
        i=0
