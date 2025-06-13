# 🚀 JavaScript Methods Masterclass
### *Your Complete Visual Learning Reference*

---

<div align="center">

![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Documentation](https://img.shields.io/badge/Documentation-4285F4?style=for-the-badge&logo=googledocs&logoColor=white)
![Learning](https://img.shields.io/badge/Learning-FF6B6B?style=for-the-badge&logo=studyverse&logoColor=white)

**📖 Last Updated:** June 2025 | **🎯 Skill Level:** Beginner to Intermediate

</div>

---

## 🏗️ Project Structure

```
📁 javascript-learning/
├── 📂 docs/
│   ├── 📄 string-methods.md      # String manipulation guide
│   ├── 📄 array-methods.md       # Array operations guide  
│   ├── 📄 object-methods.md      # Object handling guide
│   ├── 📄 number-methods.md      # Number formatting guide
│   ├── 📄 date-methods.md        # Date manipulation guide
│   └── 📄 dom-methods.md         # DOM interaction guide
├── 📂 examples/
│   ├── 🟨 string-examples.js     # Practical string examples
│   ├── 🟦 array-examples.js      # Array method examples
│   └── 🟩 object-examples.js     # Object method examples
├── 📂 practice/
│   ├── 💪 exercises.js           # Challenge exercises
│   └── ✅ solutions.js           # Solution explanations
└── 📝 README.md                  # Getting started guide
```

---

## 🎨 Visual Method Categories

<div align="center">

| 🔤 **STRINGS** | 📊 **ARRAYS** | 🗂️ **OBJECTS** | 🔢 **NUMBERS** | 📅 **DATES** |
|:---:|:---:|:---:|:---:|:---:|
| Text Magic | Data Power | Structure Pro | Math Wizard | Time Master |

</div>

---

# 🔤 STRING METHODS

<div align="center">

## 🎯 String Manipulation Arsenal

</div>

### 🔧 **Text Transformation**
```javascript
// 🎨 Case Conversion
"HELLO world".toLowerCase()     // → "hello world"
"hello WORLD".toUpperCase()     // → "HELLO WORLD"

// ✂️ Trimming Whitespace
"  hello world  ".trim()        // → "hello world"
"  hello world  ".trimStart()   // → "hello world  "
"  hello world  ".trimEnd()     // → "  hello world"
```

### 🔍 **Search & Discovery**
```javascript
// 🎯 Find Position
"Hello World".indexOf("World")          // → 6
"Hello Hello".lastIndexOf("Hello")      // → 6

// ✅ Boolean Checks
"JavaScript".includes("Script")         // → true
"JavaScript".startsWith("Java")         // → true
"JavaScript".endsWith("Script")         // → true
```

### ✂️ **Cut & Slice**
```javascript
// 🍰 Slicing Methods
"Hello World".slice(0, 5)         // → "Hello"
"Hello World".substring(6)        // → "World"
"Hello World".substr(6, 5)        // → "World"
```

### 🔄 **Replace & Repeat**
```javascript
// 🔄 Replacement Operations
"Hello World".replace("World", "JavaScript")     // → "Hello JavaScript"
"Hello Hello".replaceAll("Hello", "Hi")         // → "Hi Hi"

// 🔁 Repetition Magic
"⭐".repeat(5)                                   // → "⭐⭐⭐⭐⭐"
"0".padStart(3, "0")                            // → "000"
```

### 📊 **Complete String Methods Table**

| 🎯 **Method** | 🔧 **Purpose** | 📝 **Example** | 🎨 **Result** |
|:---:|:---:|:---:|:---:|
| `charAt(i)` | Get character at position | `"Hello".charAt(1)` | `"e"` |
| `charCodeAt(i)` | Get ASCII code | `"A".charCodeAt(0)` | `65` |
| `concat()` | Join strings | `"Hello".concat(" World")` | `"Hello World"` |
| `split()` | Split to array | `"a,b,c".split(",")` | `["a","b","c"]` |
| `match()` | Regex matching | `"Hello123".match(/\d+/)` | `["123"]` |

---

# 📊 ARRAY METHODS

<div align="center">

## 🎯 Array Manipulation Powerhouse

</div>

### 🔧 **Array Builders**
```javascript
// ➕ Adding Elements
[1, 2].push(3)           // → [1, 2, 3] (end)
[2, 3].unshift(1)        // → [1, 2, 3] (start)

// ➖ Removing Elements  
[1, 2, 3].pop()          // → 3, array becomes [1, 2]
[1, 2, 3].shift()        // → 1, array becomes [2, 3]
```

### 🔍 **Array Explorers**
```javascript
// 🕵️ Finding Elements
[1, 2, 3, 2].indexOf(2)           // → 1 (first occurrence)
[1, 2, 3, 2].lastIndexOf(2)       // → 3 (last occurrence)
[1, 2, 3].includes(2)             // → true
[1, 2, 3].find(x => x > 2)        // → 3
[1, 2, 3].findIndex(x => x > 2)   // → 2
```

### 🎨 **Array Transformers**
```javascript
// 🔄 Transformation Methods
[1, 2, 3].map(x => x * 2)              // → [2, 4, 6]
[1, 2, 3, 4].filter(x => x > 2)        // → [3, 4]
[1, 2, 3].reduce((sum, x) => sum + x)  // → 6
```

### 📊 **Array Methods Matrix**

| 🎯 **Category** | 🔧 **Method** | 📝 **Example** | 🎨 **Result** |
|:---:|:---:|:---:|:---:|
| **➕ Add/Remove** | `push()` | `[1,2].push(3)` | `[1,2,3]` |
| **➕ Add/Remove** | `splice()` | `[1,2,3].splice(1,1,'X')` | `[1,'X',3]` |
| **🔍 Search** | `includes()` | `[1,2,3].includes(2)` | `true` |
| **🎨 Transform** | `map()` | `[1,2].map(x=>x*2)` | `[2,4]` |
| **🔧 Test** | `every()` | `[2,4,6].every(x=>x%2===0)` | `true` |
| **🔧 Test** | `some()` | `[1,3,5].some(x=>x%2===0)` | `false` |
| **📊 Sort** | `sort()` | `[3,1,2].sort()` | `[1,2,3]` |
| **🔄 Combine** | `concat()` | `[1,2].concat([3,4])` | `[1,2,3,4]` |

### 🚀 **Modern Array Methods (ES6+)**
```javascript
// 🎯 Advanced Operations
[1, [2, [3]]].flat(2)                    // → [1, 2, 3]
[1, 2].flatMap(x => [x, x * 2])          // → [1, 2, 2, 4]
Array.from("hello")                      // → ["h","e","l","l","o"]
Array.of(1, 2, 3)                       // → [1, 2, 3]
```

---

# 🗂️ OBJECT METHODS

<div align="center">

## 🎯 Object Manipulation Toolkit

</div>

### 🔑 **Keys, Values & Entries**
```javascript
const user = { name: "John", age: 30, city: "Jakarta" };

// 🗝️ Extracting Data
Object.keys(user)      // → ["name", "age", "city"]
Object.values(user)    // → ["John", 30, "Jakarta"]  
Object.entries(user)   // → [["name","John"], ["age",30], ["city","Jakarta"]]
```

### 🔧 **Object Operations**
```javascript
// 🔄 Combining Objects
const obj1 = { a: 1, b: 2 };
const obj2 = { c: 3, d: 4 };
Object.assign({}, obj1, obj2)    // → { a: 1, b: 2, c: 3, d: 4 }

// 🔍 Object Validation
Object.hasOwn(user, "name")      // → true
Object.is(NaN, NaN)              // → true (better than ===)
```

### 🔒 **Object Security**
```javascript
// 🛡️ Protection Methods
const data = { secret: "password" };

Object.freeze(data)              // Cannot modify at all
Object.seal(data)                // Cannot add/remove properties
Object.preventExtensions(data)   // Cannot add new properties

// ✅ Check Protection Status
Object.isFrozen(data)            // → true/false
Object.isSealed(data)            // → true/false
Object.isExtensible(data)        // → true/false
```

### 📊 **Object Methods Reference**

| 🎯 **Method** | 🔧 **Purpose** | 📝 **Example** | 🎨 **Result** |
|:---:|:---:|:---:|:---:|
| `Object.keys()` | Get all keys | `Object.keys({a:1, b:2})` | `["a", "b"]` |
| `Object.values()` | Get all values | `Object.values({a:1, b:2})` | `[1, 2]` |
| `Object.entries()` | Get key-value pairs | `Object.entries({a:1})` | `[["a",1]]` |
| `Object.fromEntries()` | Create from entries | `Object.fromEntries([["a",1]])` | `{a:1}` |
| `Object.assign()` | Merge objects | `Object.assign({}, {a:1})` | `{a:1}` |

---

# 🔢 NUMBER METHODS

<div align="center">

## 🎯 Number Formatting & Validation

</div>

### 🎨 **Number Formatting**
```javascript
const num = 3.14159;

// 🎯 Precision Control
num.toFixed(2)           // → "3.14"
num.toPrecision(4)       // → "3.142"
num.toExponential(2)     // → "3.14e+0"

// 🌍 Locale Formatting
(1234.5).toLocaleString('id-ID')    // → "1.234,5"
(1234.5).toLocaleString('en-US')    // → "1,234.5"
```

### ✅ **Number Validation**
```javascript
// 🔍 Type Checking
Number.isInteger(4.0)        // → true
Number.isFinite(Infinity)    // → false
Number.isNaN(NaN)           // → true
Number.isSafeInteger(9007199254740991)  // → true

// 🔄 Parsing
Number.parseInt("10", 2)     // → 2 (binary)
Number.parseFloat("3.14")    // → 3.14
```

### 📊 **Number Methods Table**

| 🎯 **Method** | 🔧 **Purpose** | 📝 **Example** | 🎨 **Result** |
|:---:|:---:|:---:|:---:|
| `toFixed()` | Fixed decimal places | `3.14159.toFixed(2)` | `"3.14"` |
| `toString()` | Convert to string | `255..toString(16)` | `"ff"` |
| `Number.isInteger()` | Check if integer | `Number.isInteger(4.0)` | `true` |
| `Number.parseFloat()` | Parse float | `Number.parseFloat("3.14")` | `3.14` |

---

# 📅 DATE METHODS

<div align="center">

## 🎯 Time Manipulation Master

</div>

### 📊 **Date Components**
```javascript
const now = new Date();

// 📅 Getting Date Parts
now.getFullYear()    // → 2025
now.getMonth()       // → 5 (June, 0-based)
now.getDate()        // → 13
now.getDay()         // → 5 (Friday, 0=Sunday)

// ⏰ Getting Time Parts
now.getHours()       // → 14
now.getMinutes()     // → 30
now.getSeconds()     // → 45
```

### 🎨 **Date Formatting**
```javascript
const date = new Date();

// 🌍 Locale Formatting
date.toLocaleDateString('id-ID')     // → "13/6/2025"
date.toLocaleTimeString('id-ID')     // → "14.30.45"
date.toLocaleString('id-ID')         // → "13/6/2025 14.30.45"

// 📊 Standard Formats
date.toISOString()                   // → "2025-06-13T07:30:45.123Z"
date.toDateString()                  // → "Fri Jun 13 2025"
```

### ⚡ **Date Utilities**
```javascript
// 🔢 Timestamps
Date.now()                    // → 1718276245123
new Date().getTime()          // → 1718276245123
Date.parse("2025-06-13")      // → 1718236800000
```

### 📊 **Date Methods Reference**

| 🎯 **Category** | 🔧 **Method** | 📝 **Example** | 🎨 **Result** |
|:---:|:---:|:---:|:---:|
| **📅 Get** | `getFullYear()` | `new Date().getFullYear()` | `2025` |
| **📅 Get** | `getMonth()` | `new Date().getMonth()` | `5` |
| **⏰ Get** | `getHours()` | `new Date().getHours()` | `14` |
| **🎨 Format** | `toLocaleDateString()` | `date.toLocaleDateString('id-ID')` | `"13/6/2025"` |
| **⚡ Utility** | `Date.now()` | `Date.now()` | `1718276245123` |

---

# 🌐 DOM METHODS BONUS

<div align="center">

## 🎯 Web Interaction Toolkit

</div>

### 🔍 **Element Selection**
```javascript
// 🎯 Single Element Selection
document.getElementById("myId")
document.querySelector(".myClass")
document.querySelector("div.container")

// 📊 Multiple Element Selection  
document.getElementsByClassName("myClass")
document.getElementsByTagName("div")
document.querySelectorAll("div.item")
```

### 🔧 **Element Manipulation**
```javascript
// 🏗️ Creating & Adding
const newDiv = document.createElement("div");
newDiv.textContent = "Hello World";
document.body.appendChild(newDiv);

// 🎨 Attributes & Events
element.setAttribute("class", "highlight");
element.addEventListener("click", handleClick);
```

---

# 🎯 LEARNING ROADMAP

<div align="center">

## 🚀 Your JavaScript Journey

</div>

### 📅 **Week 1-2: Foundations**
```javascript
// 🎯 Focus Areas
✅ String Methods (charAt, slice, replace, split)
✅ Basic Array Methods (push, pop, indexOf, includes)
✅ Number Formatting (toFixed, toString)

// 💪 Practice Project: Text Analyzer
const analyzeText = (text) => {
  return {
    length: text.length,
    words: text.split(' ').length,
    uppercase: text.toUpperCase(),
    reversed: text.split('').reverse().join('')
  };
};
```

### 📅 **Week 3-4: Intermediate**
```javascript
// 🎯 Focus Areas
✅ Array Iteration (map, filter, reduce, forEach)
✅ Object Methods (keys, values, entries, assign)
✅ Date Manipulation (formatting, calculations)

// 💪 Practice Project: Data Processor
const processUsers = (users) => {
  return users
    .filter(user => user.age >= 18)
    .map(user => ({
      ...user,
      fullName: `${user.firstName} ${user.lastName}`,
      isAdult: true
    }))
    .sort((a, b) => a.age - b.age);
};
```

### 📅 **Week 5-6: Advanced**
```javascript
// 🎯 Focus Areas
✅ Advanced Array Methods (flat, flatMap, reduce combinations)
✅ Object Protection (freeze, seal, preventExtensions)
✅ Complex String Operations (regex, advanced parsing)

// 💪 Practice Project: Mini Framework
const createValidator = (rules) => {
  return (data) => {
    return Object.entries(rules).every(([key, rule]) => {
      const value = data[key];
      return rule.test ? rule.test(value) : rule(value);
    });
  };
};
```

---

# 🛠️ PRACTICE TEMPLATES

<div align="center">

## 🎯 Hands-On Learning Tools

</div>

### 🧪 **Method Testing Template**
```javascript
// 🔬 Universal Method Tester
const testMethod = (methodName, input, expected, methodFn) => {
  console.log(`🧪 Testing: ${methodName}`);
  console.log(`📝 Input: ${JSON.stringify(input)}`);
  console.log(`🎯 Expected: ${JSON.stringify(expected)}`);
  
  const result = methodFn(input);
  console.log(`✅ Result: ${JSON.stringify(result)}`);
  console.log(`${result === expected ? '✅ PASS' : '❌ FAIL'}`);
  console.log('---');
};

// 🎯 Example Usage
testMethod('toUpperCase', 'hello', 'HELLO', (str) => str.toUpperCase());
```

### 🎯 **Challenge Generator**
```javascript
// 🎮 Random Challenge Generator
const challenges = {
  string: [
    "Create a function that reverses words in a sentence",
    "Build a simple password strength checker",
    "Make a function that removes vowels from text"
  ],
  array: [
    "Find the second largest number in an array",
    "Group array elements by their first letter",
    "Create a function that removes duplicates"
  ],
  object: [
    "Merge multiple user objects safely",
    "Create a deep clone function",
    "Build a simple object validator"
  ]
};

const getRandomChallenge = (type) => {
  const list = challenges[type];
  return list[Math.floor(Math.random() * list.length)];
};
```

---

# 🎉 FINAL THOUGHTS

<div align="center">

## 🚀 Your JavaScript Success Formula

**📚 LEARN** → **🔧 PRACTICE** → **🏗️ BUILD** → **🔄 REPEAT**

### 💡 Pro Tips for Mastery

🎯 **Consistency Over Intensity**: 30 minutes daily beats 5 hours weekly  
🔧 **Practice with Real Data**: Use APIs, CSV files, user inputs  
🏗️ **Build Mini Projects**: Each method should solve a real problem  
🤝 **Share Your Learning**: Teach others what you discover  

### 🔗 Essential Resources

- 📖 [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript) - The ultimate reference
- 🎮 [JavaScript.info](https://javascript.info/) - Interactive tutorials
- 🔧 Browser DevTools - Your debugging best friend
- 💻 [CodePen](https://codepen.io/) - Test ideas quickly

</div>

---

<div align="center">

**Made with ❤️ for JavaScript Learners**

*Happy Coding! 🚀*

---

![Footer](https://img.shields.io/badge/Keep%20Learning-Keep%20Growing-FF6B6B?style=for-the-badge&logo=javascript&logoColor=white)

</div>
