# 🎯 Mock Interview Set 1: Warm-Up Round

**Difficulty**: ⭐ Easy | **Duration**: ~30 min | **Focus**: Introduction + Basic Concepts + Easy DSA

---

## Round 1: Introduction (2-3 min)

### Q: Tell me about yourself. (40-50 seconds)

**Answer**:
"Good morning/afternoon! I am **Gaurav Kumar Mehta**, a final-year B.Tech student in Computer Science at JIS College of Engineering, Kalyani. I specialize in **full-stack web development** using the MERN stack — MongoDB, Express, React, and Node.js.

I've built projects like **FashionHub**, an e-commerce platform that improved buying efficiency by 35%, and a **Bike & Scooter Rental System** with real-time tracking and integrated payments.

I also hold a **patent for AI-based tumor detection** using deep learning. I'm passionate about building scalable, user-centric applications and I'm eager to contribute to a dynamic engineering team. Thank you!"

### Q: Walk me through your education

**Answer**:
"I'm pursuing B.Tech in Computer Science from JIS College of Engineering with a **CGPA of 7.63**. I completed my 12th from VJ International School, Bhagalpur with CBSE board, and my 10th from Sri Rani Saraswati Vidya Mandir, Forbesganj."

### Q: What technologies are you comfortable with?

**Answer**:
"My primary stack is **MERN** — MongoDB, Express, React, Node.js. I'm also proficient in **Python and C** for DSA, and I'm familiar with **SQL databases** alongside NoSQL. For tools, I use **Git/GitHub** for version control and have basic exposure to AI/ML concepts."

---

## Round 2: Technical Concepts (10 min)

### Q: What is the difference between `let`, `var`, and `const`?

**Answer**:
"`var` is **function-scoped** and can be re-declared. `let` is **block-scoped** and cannot be re-declared in the same scope. `const` is also block-scoped but cannot be **re-assigned** after initialization. Both `let` and `const` have a Temporal Dead Zone before their declaration line."

### Q: What is an API? Have you used one?

**Answer**:
"API stands for Application Programming Interface. It's a set of rules that allows two software systems to communicate. In my projects, I've used **REST APIs** — for example, in my Bike Rental app, my React frontend makes HTTP requests (GET, POST, PUT, DELETE) to my Express.js backend, which processes the request and interacts with the MongoDB database."

### Q: What is the CSS Box Model?

**Answer**:
"Every HTML element is treated as a box with four layers: **Content** (the actual text/image), **Padding** (space between content and border), **Border** (the edge), and **Margin** (space outside the border). I use `box-sizing: border-box` to make width calculations include padding and border."

### Q: What are Semantic HTML tags? Give examples

**Answer**:
"Semantic tags describe their purpose clearly, like `<header>`, `<nav>`, `<main>`, `<article>`, and `<footer>`. They improve accessibility for screen readers and help search engines understand page structure, which is good for SEO."

---

## Round 3: DSA - Easy (10-15 min)

### Q: Two Sum (Array)

**Problem**: Given `nums = [2,7,11,15]` and `target = 9`, find indices of two numbers that add up to target.
**Answer**:

```javascript
function twoSum(nums, target) {
  const map = {};
  for (let i = 0; i < nums.length; i++) {
    const diff = target - nums[i];
    if (diff in map) return [map[diff], i];
    map[nums[i]] = i;
  }
}
// Output: [0, 1] because nums[0] + nums[1] = 2 + 7 = 9
```

**Explanation**: "I use a hash map to store each number and its index. For each element, I check if `target - nums[i]` already exists in the map. If yes, I return both indices. Time: O(n), Space: O(n)."

### Q: Reverse a String

**Problem**: Reverse `"hello"` → `"olleh"`
**Answer**:

```javascript
// Method 1: Built-in
"hello".split('').reverse().join(''); // "olleh"

// Method 2: Loop (interviewers prefer this)
function reverseString(s) {
  let result = '';
  for (let i = s.length - 1; i >= 0; i--) {
    result += s[i];
  }
  return result;
}
```

### Q: Check Valid Parentheses

**Problem**: Given `s = "()[]{}"`, check if all brackets are properly closed.
**Answer**:

```javascript
function isValid(s) {
  const stack = [];
  const map = { ')': '(', '}': '{', ']': '[' };
  for (const char of s) {
    if ('([{'.includes(char)) {
      stack.push(char);
    } else {
      if (stack.pop() !== map[char]) return false;
    }
  }
  return stack.length === 0;
}
```

**Explanation**: "I use a **stack**. Push opening brackets, and for closing brackets, check if the top of the stack matches. If the stack is empty at the end, it's valid. Time: O(n)."

---

## Round 4: Quick HR (5 min)

### Q: Why do you want to work as a software developer?

**Answer**:
"I love the problem-solving aspect — taking a real-world problem and building a digital solution. When I built FashionHub, seeing actual users navigate through my interface and the buying process being smoother was deeply satisfying. Software development lets me create things that have a tangible impact."

### Q: Are you open to relocation?

**Answer**:
"Yes, absolutely. I'm open to relocating anywhere in India for the right opportunity. I'm adaptable and excited to work in different environments."
