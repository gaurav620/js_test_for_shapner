# 🎯 Mock Interview Set 2: Mid-Level Round

**Difficulty**: ⭐⭐ Easy-Medium | **Duration**: ~40 min | **Focus**: Projects Deep-Dive + DSA + JS Concepts + HR

---

## Round 1: Introduction & Background (3 min)

### Q: Give a brief introduction

*(Use the same 40-50 sec script from Set 1)*

### Q: Tell me about your patent

**Answer**:
"I co-authored a patent for an **AI-based tumor detection and mental health assessment system** using Convolutional Neural Networks (CNN). The system analyzes medical imaging data to detect tumors and also performs mental health screening. It aims to improve early diagnosis and assist doctors in treatment planning. This was published in 2025."

### Q: What is your CGPA and do you have any backlogs?

**Answer**:
"My current CGPA is **7.63** and I have **no active backlogs**. I've maintained a consistent academic record throughout my B.Tech."

---

## Round 2: Project Deep-Dive (15 min)

### Q: Explain the architecture of your FashionHub project

**Answer**:
"FashionHub follows an **MVC architecture**:

- **Model**: MongoDB schemas for Users, Products, and Orders.
- **View**: EJS templates for server-side rendering with dynamic data binding.
- **Controller**: Express.js routes handle business logic — user authentication, product CRUD, cart management, and checkout flow.
- The frontend uses **HTML/CSS/JavaScript** for responsiveness and interactivity."

### Q: How did you implement the category filtering in FashionHub?

**Answer**:
"I created a **Category** collection in MongoDB, with each product having a `categoryId` reference. When a user clicks a category button, the frontend sends a GET request to `/products?category=<id>`. The Express controller queries MongoDB using `Product.find({ categoryId })` and renders only the matching products. This is more efficient than client-side filtering because it reduces the data transferred."

### Q: In the Bike Rental project, why did you choose React over EJS?

**Answer**:
"The Bike Rental System needed a **highly interactive SPA** experience — features like real-time availability checking, dynamic pricing, and instant booking status updates. React's **Virtual DOM** and **component-based architecture** allow immediate UI updates without full page reloads, which EJS can't do efficiently since it's server-rendered."

### Q: How do you handle authentication in your Bike Rental app?

**Answer**:
"I implemented **JWT-based authentication**. When a user logs in, the server validates credentials against the database and returns a **JSON Web Token**. This token is stored in `localStorage` on the client side and sent with every subsequent API request in the `Authorization` header. The server middleware verifies the token before processing protected routes."

### Q: What was the toughest bug you faced and how did you solve it?

**Answer**:
"In the Bike Rental app, I faced a **race condition** where two users could book the same vehicle simultaneously. The issue was that the 'availability check' and 'booking confirmation' were separate database operations. I solved it by using **MongoDB's `findOneAndUpdate` with conditions** — atomically checking availability and marking the vehicle as booked in a single operation. This eliminated the race condition."

---

## Round 3: DSA (15 min)

### Q: Find the Maximum Subarray Sum (Kadane's Algorithm)

**Problem**: Find the contiguous subarray with the largest sum in `[-2,1,-3,4,-1,2,1,-5,4]`.
**Answer**:

```javascript
function maxSubArray(nums) {
  let maxSum = nums[0];
  let currentSum = nums[0];
  for (let i = 1; i < nums.length; i++) {
    currentSum = Math.max(nums[i], currentSum + nums[i]);
    maxSum = Math.max(maxSum, currentSum);
  }
  return maxSum;
}
// Output: 6 (subarray [4,-1,2,1])
```

**Explanation**: "At each index, I decide: start a new subarray from this element, or extend the previous subarray. I keep track of the maximum sum seen so far. Time: O(n), Space: O(1)."

### Q: Reverse a Linked List

**Problem**: Reverse a singly linked list.
**Answer**:

```javascript
function reverseList(head) {
  let prev = null;
  let curr = head;
  while (curr) {
    let next = curr.next;
    curr.next = prev;
    prev = curr;
    curr = next;
  }
  return prev;
}
```

**Explanation**: "I use three pointers — `prev`, `curr`, `next`. At each step, I reverse the `next` pointer of the current node to point to `prev`, then move all pointers forward. Time: O(n), Space: O(1)."

### Q: Implement a Queue using Two Stacks

**Answer**:

```javascript
class MyQueue {
  constructor() {
    this.stack1 = []; // for push
    this.stack2 = []; // for pop
  }
  push(x) {
    this.stack1.push(x);
  }
  pop() {
    if (this.stack2.length === 0) {
      while (this.stack1.length > 0) {
        this.stack2.push(this.stack1.pop());
      }
    }
    return this.stack2.pop();
  }
  peek() {
    if (this.stack2.length === 0) {
      while (this.stack1.length > 0) {
        this.stack2.push(this.stack1.pop());
      }
    }
    return this.stack2[this.stack2.length - 1];
  }
}
```

---

## Round 4: HR Round (7 min)

### Q: What are your strengths and weaknesses?

**Answer**:

- **Strength**: "I'm highly **persistent**. When I encountered the race condition bug in my rental project, I didn't patch it — I researched atomic database operations and implemented a proper solution. I believe in fixing things the right way."
- **Weakness**: "I tend to **over-engineer** initial solutions. I've been actively working on this by first building an MVP, getting feedback, and then iterating."

### Q: Where do you see yourself in 5 years?

**Answer**:
"In 5 years, I see myself as a **Senior Full-Stack Engineer** with expertise in building scalable distributed systems. I want to lead small teams, mentor junior developers, and contribute to architectural decisions. I'm also interested in exploring **AI integration in web applications**, given my patent background."

### Q: How do you handle pressure and tight deadlines?

**Answer**:
"I break big tasks into smaller **milestones** with realistic deadlines. During my final year, I had my project submission, patent filing, and IBM SkillsBuild certification happening simultaneously. I used a priority matrix — urgent + important things first, delegated team tasks clearly, and communicated progress daily. Everything was delivered on time."

### Q: Do you have any questions for us?

**Answer** *(Always ask!)*:
"Yes, two questions:

1. What does the typical **tech stack** look like at companies I'd be interviewing with?
2. How is the **mentorship** structured after I clear the mock interview — will I get company-specific preparation?"
