# Operators, Branching, Loops

## Easy

1. Write a program to add 5 numbers. The value of numbers are num1=5, num2=13, num3=7, num4=21 and num5=48.
    ```js
        let sum = 0
        const arr = [5,13,7,21,48];
        arr.map(ele => sum = sum + ele)
        console.log(sum) // 94
    ```

1. Write a program to take a number input from user and determine whether the number is odd or even.
    ```js
    const evenOrOdd = (num) => num % 2===0?'even':'odd'
    console.log(evenOrOdd(2)) // even
    ```

1. Write a program to find the maximum and minimum out of two given numbers. The numbers are num1=129 and num2=251.

    ```js
    const findGreater = (num,num1) => num>num1?num:num1;
    console.log(findGreater(129,251)) // 251
    ```

1. Write a program to find the maximum out of three given numbers. The numbers are num1=8, num2=23 and num3=17.
    ```js
    //version 1
    const findGreater = (num,num1,num2) => {
        if(num>num1 && num>num2){
            return num
        }else if(num1>num && num1>num2){
            return num1
        }else {
            return num2
        }
    }
    console.log(findGreater(8,23,17))
    //version 2
    const findGreater = (...rest) => Math.max(...rest)
    console.log(findGreater(8,23,17)) //23
    ```

1. Write a program to find the minimum out of three given numbers. The numbers are num1=35, num2=29 and num3=46.
    ```js
    const findSmaller = (...rest) => Math.max(...rest)
    console.log(findSmaller(35,29,46)) // 29
    ```
1. Write program to take a month as an input from the user and find out whether the month has 31 days or not.
    ```html
    <!-- HTML file -->
    <input type="month" id="month" />
    <button id="find-days">Find Days</button>
    <p id="message"></p>
    ```
    ```js
    //Js file
    const [monthInput, findDays, message] = [
        "month",
        "find-days",
        "message"
    ].map((item) => document.querySelector(`#${item}`));

    const numberOfDaysInMonth = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31];
    const monthName = [
        "January",
        "February",
        "March",
        "April",
        "May",
        "June",
        "July",
        "August",
        "September",
        "October",
        "November",
        "December"
    ];

    findDays.addEventListener("click", () => {
        let index = Number(monthInput.value.split("-")[1]) - 1;
        message.innerText = `Number of day's in ${monthName[index]}  ${numberOfDaysInMonth[index]}`;
    });

    ```

## Intermediate

1. Fizzbuzz - Write a program to return an array from 1 to 100. But for every multiple of 3, replace the number with "Fizz", for every multiple of 5, replace the number with "Buzz" and for every multiples of 3 & 5, replace with "FizzBuzz".

    Your output should look something like this `1, 2, Fizz, 4, Buzz, Fizz, 7, 8, Fizz, Buzz, 11, Fizz, 13, 14, FizzBuzz, 16, 17 ..... `

    ```js
    const getFizzBuzz = () => {
    let fizzBuzzArray = [];
    for (let i = 1; i <= 50; i++) {
        if (i % 3 === 0 && i % 5 === 0){
            fizzBuzzArray.push("FizzBuzz");
        } else if (i % 5 === 0) {
            fizzBuzzArray.push("Buzz");
        } else if (i % 3 === 0) {
            fizzBuzzArray.push("Fizz");
        } else {
            fizzBuzzArray.push(i);
        }
    }
    return fizzBuzzArray;
    };

    getFizzBuzz();
    ```

1. Print the following star pattern :-

    \* \
    \* \* \
    \* \* \* \
    \* \* \* \* \
    \* \* \* \* \*

    ```js
    let addNTimes = (num, string) => {
        let tempString = "";
        for (let i = 0; i < num; i++) {
            tempString += string;
        }
        return tempString;
    };
    addNTimes(5, "*");
    for (let i = 1; i <= 5; i++) {
        console.log(addNTimes(i, "*"));
    }
    //using inbuilt functions
    for (let i = 1; i <= 5; i++) {
        console.log('*'.repeat(i));
    }
    ```

1. Write a program to take a number input from user and print multiplication table 12 times for that number.
    ```html
    <input type="number" id="number" />
    <button id="multiplication-table">Multiplication Table</button>
    <p id="table"></p>
    ```
    ```js
    [inputNumber, multiplicationNumber, table] = [
    "number",
    "multiplication-table",
    "table"
    ].map((item) => document.querySelector(`#${item}`));

    multiplicationNumber.addEventListener("click", () => {
    for (let i = 1; i <= 12; i++) {
        console.log(
        `${inputNumber.value} X ${i} = ${Number(inputNumber.value) * i}`
        );
    }
    });

    ```

1. Write a program to return a Fibonacci series : 0,1,1,2,3,5,8,13,21....

    ```js
    const generateFabonicca = (upTo) => {
    const phi1 = (1 + Math.sqrt(5)) / 2;
    const phi2 = (1 - Math.sqrt(5)) / 2;
    const fabonicaArray = [];
    for (let i = 0; i <= upTo; i++) {
        let numerator = Math.pow(phi1, i) - Math.pow(phi2, i);
        let denominator = Math.sqrt(5);
        let nThElement = parseInt(numerator / denominator);
        fabonicaArray.push(nThElement);
    }
    return fabonicaArray;
    };
    console.log(generateFabonicca(50));    
    ```

1. Write a program to take an input from a user and find its Factorial.
   `Example: Factorial of 5 is 120`

    ```js
    const generateFactorial = (num) => {
    let factorial = 1;
    for (let i = 2; i <= num; i++) {
        factorial *= i;
    }
    return factorial;
    };
    console.log(generateFactorial(5));
    ```
1. Write a Program to take a number input from user and find if the number is Prime or not.

    ```js
    const isPrime = num => {
    let i;
    for (i = 2; i <= Math.floor(Math.sqrt(num)); i++) {
        if (num % i === 0) break;
    }
    return i === Math.floor(Math.sqrt(num)) + 1 ? 'prime' : 'not Prime';
    };
    console.log(isPrime(5)); //prime

    ```
1. Write a program to take a day as an input and determine whether it is a weekday or weekend.
   `Example: Tuesday is weekday.`
    ```js
    const daysInWeek = [
        'Monday',
        'Tuesday',
        'Wednesday',
        'Thursday',
        'Friday',
        'Saturday',
        'Sunday',
    ];
    const determineDay = day => {
        if (daysInWeek.includes(day)) {
            return day === 'sunday' || day === 'saturday' ? 'Weekend' : 'Weekday';
        } else {
            return 'Enter valid input';
        }
    };
    console.log(determineDay(prompt('Enter the day')));

    ```