Practice Questions:
Sure! Here are the simplest questions for each of the cases to practice with:

**A. Regex questions for `.replace()` method:**

1. **Basic substitution:**
   Question: Replace all occurrences of the word "apple" with "orange" in the string: "I have an apple and a green apple."
   
2. **Case-insensitive replacement:**
   Question: Replace all occurrences of the word "hello" (case-insensitive) with "hi" in the string: "Hello, World! hello, everyone!"

3. **Replacing multiple patterns:**
   Question: Replace both "red" and "blue" with "green" in the string: "The sky is blue, and the flower is red."

4. **Backreferences in replacement:**
   Question: Replace all occurrences of "John Doe" with "Doe, John" in the string: "My name is John Doe, and I like John Doe."

5. **Escaping characters:**
   Question: Replace all occurrences of the word "dot." with "period" in the string: "I like dot. in my sentences."

6. **Replacing numbers:**
   Question: Add leading zeros to all numbers in the string: "The product costs $25 and the quantity is 100."

7. **Replacing with a callback function:**
   Question: Replace all occurrences of the word "bird" with "dove" and "cat" with "kitten" using a callback function in the string: "The bird flew away, and the cat chased a mouse."

8. **Replacing with named groups:**
   Question: Replace the date in the format "dd/mm/yyyy" with "yyyy-mm-dd" using named groups in the string: "The event date is 21/07/2023."

These simple questions should help you practice and get comfortable with using regular expressions and the `.replace()` method for various scenarios. Happy practicing!

**B. Regex questions for `.match()` method:**

1. **Simple pattern matching:**
   Question: Find all occurrences of the word "apple" in the string: "I have an apple and a banana."

2. **Case-insensitive matching:**
   Question: Find all occurrences of the word "book" (case-insensitive) in the string: "I have a Book and a book."

3. **Matching numbers:**
   Question: Extract all numbers from the string: "The product costs $25 and the quantity is 100."

4. **Matching multiple patterns:**
   Question: Find all occurrences of either "red" or "blue" in the string: "The sky is blue, and the flower is red."

5. **Matching word boundaries:**
   Question: Find all occurrences of the word "at" as whole words in the string: "The cat sat on the mat."

6. **Extracting groups:**
   Question: Extract all the dates (in dd/mm/yyyy format) from the string: "The event dates are 01/05/2023 and 15/06/2023."

7. **Named capturing groups:**
   Question: Extract the area code and local number from a phone number in the format "(123) 456-7890".

8. **Global matching:**
   Question: Find all occurrences of the word "hello" in the string: "hello hello hello" using the global flag.

9. **Non-capturing groups:**
    Question: Find all occurrences of "hi" or "hello" without capturing the individual matches in the string: "Hi there, hello!"

These simple practice questions should help you get started with regular expressions and familiarize yourself with the `.replace()` and `.match()` methods. Remember to experiment with different patterns and flags to build your confidence in using regex effectively.



----------------------------------------------------------------------------------

## SOLUTIONS

#### A(1) Answer
```
const string = "I have an apple and a green apple.";
const regex = /apple/g;
const newString = string.replace(regex, "orange");
console.log(newString); // Output: "I have an orange and a green orange."
```


#### A(2) Answer
```
const inputString = "Hello, World! hello, everyone!, Nice to write hello again Hello";
const regex = /\bHello\b/g;

const outputString = inputString.replace(regex, (match) => {
  return match.charAt(0).toUpperCase() === 'H' ? 'Hi' : 'hi';
});

console.log(outputString); // Output: "Hi, World! hi, everyone!, Nice to write hi again Hi"
```


#### A(3) Answer
```
const inputString = "The sky is blue, and the flower is red.";
const regex = /red|blue/gi;
const replacement = "green";

const outputString = inputString.replace(regex, replacement);

console.log(outputString); // Output: "The sky is green, and the flower is green."
```

```
/* Replacing multiple patterns: Question: Replace "red" with "white"
and "blue" with "green" in the string: "The sky is blue, and the flower is red." */

const inputString = "The sky is blue, and the flower is red.";
const outputString = inputString
  .replace(/red/gi, "white")
  .replace(/blue/gi, "green");

console.log(outputString); // Output: "The sky is green, and the flower is white."
```


#### A(4) Answer

```
const inputString = "My name is John Doe, and I like John Doe.";
const regex = /(\bJohn\b)\s(\bDoe\b)/gi;
const replacement = "$2, $1";
const outputString = inputString.replace(regex, replacement);

console.log(outputString); // Result: "My name is Doe, John, and I like Doe, John."
```

#### A(5) Answer
```
const inputString = "I like dot. in my sentences.";
const replacedString = inputString.replace(/dot\./g, "period");

console.log(replacedString); // Output: "I like period in my sentences."
```


#### A(6) Answer
```
const inputString = "The product costs $25 and the quantity is 10.";
const stringWithLeadingZeros = inputString.replace(/\d+/g, (match) => {
  return match.padStart(3, '0');
});

console.log(stringWithLeadingZeros);
// Output: "The product costs $025 and the quantity is 010."
```


#### A(7) Answer
```
const inputString = "The bird flew away, and the cat chased a mouse.";
const replacedString = inputString.replace(/bird|cat/g, match => {
  return match === 'bird' ? 'dove' : 'kitten';
});

console.log(replacedString);
// Output: "The dove flew away, and the kitten chased a mouse."
```


#### A(8) Answer
```
const inputString = "The event date is 21/07/2023.";
const replacedString = inputString.replace(
  /(?<day>\d{2})\/(?<month>\d{2})\/(?<year>\d{4})/g,
  "$<year>-$<month>-$<day>"
);

console.log(replacedString);
// Output: "The event date is 2023-07-21."
```


#### B(1) Answer
```
const inputString = "I have an apple and a banana.";
const occurrences = inputString.match(/apple/g);

console.log(occurrences); // Output: ["apple"]
```

```
const string = "Size: 64GB<i class='a-icon a-icon-text-separator' role='img' aria-label='|'></i>Color: Purple<i class='a-icon a-icon-text-separator' role='img' aria-label='|'></i>Service Provider: Unlocked<i class='a-icon a-icon-text-separator' role='img' aria-label='|'></i>Product grade: Renewed";

const occurrences = string.match(/(class=')(.*?)('|')/g);

console.log(occurrences); // Output: ["class='a-icon a-icon-text-separator'", "class='a-icon a-icon-text-separator'", "class='a-icon a-icon-text-separator'"]
```

#### B(2) Answer
```
const inputString = "I have a Book and a book.";
const occurrences = inputString.match(/book/gi);

console.log(occurrences); // Output: ["Book", "book"]
```


#### B(3) Answer
```
const inputString = "The product costs $25 and the quantity is 100.";
const numbers = inputString.match(/\d+/g);

console.log(numbers); // Output: ["25", "100"]
```

#### B(4) Answer
```
const inputString = "The sky is blue, and the flower is red.";
const occurrences = inputString.match(/red|blue/gi);

console.log(occurrences); // Output: ["blue", "red"]
```


#### B(5) Answer
```
NULL Solution
```

#### B(6) Answer
```
const str = "The event dates are 01/05/2023 and 15/06/2023.";
const pattern = /\b(\d{2}\/\d{2}\/\d{4})\b/g;

const matches = str.match(pattern);

console.log(matches); // Output: ["01/05/2023", "15/06/2023"]
```


#### B(7) Answer
```
const phoneNumber = "(123) 456-7890";
const pattern = /\((?<areaCode>\d{3})\)\s(?<localNumber>\d{3}-\d{4})/;

const match = phoneNumber.match(pattern);

if (match) {
  const areaCode = match.groups.areaCode;
  const localNumber = match.groups.localNumber;

  console.log("Area Code:", areaCode); // Output: Area Code: 123
  console.log("Local Number:", localNumber); // Output: Local Number: 456-7890
} else {
  console.log("Invalid phone number format.");
}
```

#### B(8) Answer
```
const phoneNumber = "(123) 456-7890";
const pattern = /\((?<areaCode>\d{3})\)\s(?<localNumber>\d{3}-\d{4})/;

const match = phoneNumber.match(pattern);

if (match) {
  const areaCode = match.groups.areaCode;
  const localNumber = match.groups.localNumber;

  console.log("Area Code:", areaCode); // Output: Area Code: 123
  console.log("Local Number:", localNumber); // Output: Local Number: 456-7890
} else {
  console.log("Invalid phone number format.");
}
```

#### B(9) Answer
```
const str = "Hi there, hello!";
const pattern = /(?:hi|hello)/gi;

const matches = str.match(pattern);

console.log(matches); // Output: ["Hi", "hello"]
```
