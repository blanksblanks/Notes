FizzBuzz

```
for i in xrange(1, 101):
    if i % 15 == 0:
        print "FizzBuzz"
    elif i % 3 == 0:
        print "Fizz"
    elif i % 5 == 0:
        print "Buzz"
    else:
        print i
```

isPalindrome

```
def ispalindrome(word):
    if len(word) < 2: return True
    if word[0] != word[-1]: return False
    return ispalindrome(word[1:-1])

def ispalindrome(word):
    return word == word[::-1]
```

can a string be a palindrome?

```
def is_scrambled_pal(s)
  odds = {}
  s.split('').each do |c|
    if odds[c]
      odds.delete(c)
    else
      odds[c] = c
    end
  end
  return (odds.length < 2) ? true : false
end

function isScrambledPalindrome( input ) {
    var chars = {};
    input.split("").forEach(function(char) {
    if (chars[char]) {
        delete chars[char]
    } else {
        chars[char] = "odd" }
    });
    return (Object.keys(chars).length <= 1);
}
```

isPrime

```
def isprime(n):
    for m in range(2, int(n**0.5)+1):
        if not n%m:
            return False
    return True
```

If a number n is not a prime, it can be factored into two factors a and b:n = a*b
If both a and b were greater than the square root of n, a*b would be greater than n. So at least one of those factors must be less or equal to the square root of n, and to check if n is prime, we only need to test for factors less than or equal to the square root."

Fibonacci

```
int fibonacci(int i) {
  if (i==0 || i==1) return i;
  return fibonacci(i-1) + fibonacci(i-2);
}

# Cached
int[] fib = new int[max]
int fibonacci(int i) {
  if (i==0 || i == 1) return i;
  if (fib[i] != 0) return fib[i];
  fib[i] = fibonacci(i-1) + fibonacci(i-2);
  return fib[i];
}

def fib(n):
    storage = {}
    a,b = 0,1
    for i in range(n):
        a,b = b, a+b
        storage[n] = a
    return a
```

group anagram

```
def groupAnagrams(words):
    anagrams = {};
    for word in words:
        sorted = word.sort()
        if anagrams[sorted]:
            anagrams[sorted].push(word)
        else:
            anagrams[sorted] = [word]
    return anagrams;


import collections

# O(mlogm) - logm for sorting
def sort_prehash(word):
    return ''.join(sorted(word))

#O(m) - m is length of word
def count_letters_prehash(word):
    return tuple(collections.Counter(word).items())
#O(n) * hash function value
def group_anagrams(words, hash_function):
    result = {}
    for w in words:
        s = hash_function(w.lower())
        if s in result:
            result[s] |= {w}
        else:
            result[s] = {w}
    return result.values()
```

max, min, avg stack	save max, min, avg at each node of stack; pop, push
factorial

```
def factorial(n):
    if n == 0:
        return 1
    else:
        return n * factorial(n-1)

function factorial(n) {
    var fact = 1;

    for (var i = fact; i <= n; i++) {
        fact *= i;
    }

    return fact;
};
```

Spiral Matrix: Given a matrix, print out the numbers in spiral order.
ex.

```
matrix = [[11, 12, 13, 14, 15],
          [21, 22, 23, 24, 25],
          [31, 32, 33, 34, 35],
          [41, 42, 43, 44, 45]];
```
Prints, 11, 12, 13, 14, 15, 25, 35, 45, 44, 43, 42, 41, 31, 21, 22, 23, 24, 34, 33, 32

```
public static void main(String[] args) {
		int[][] matrix = {{11, 12, 13, 14, 15},{21, 22, 23, 24, 25},{31, 32, 33, 34, 35},{41, 42, 43, 44, 45}};
		spiralOrder(matrix);
	}

	static void spiralOrder(int[][] matrix)
	{
	     if(matrix.length == 0)
	         return;
	     // Initialize our four indexes
	     int top = 0;
	     int down = matrix.length - 1;
	     int left = 0;
	     int right = matrix[0].length - 1;

	     while(true)
	     {
	         // Print top row
	         for(int j = left; j <= right; ++j) System.out.print(matrix[top][j] + " ");
	         top++;
	         if(top > down || left > right) break;
	         //Print the rightmost column
	         for(int i = top; i <= down; ++i) System.out.print(matrix[i][right] + " ");
	         right--;
	         if(top > down || left > right) break;
	         //Print the bottom row
	         for(int j = right; j >= left; --j) System.out.print(matrix[down][j] + " ");
	         down--;
	         if(top > down || left > right) break;
	         //Print the leftmost column
	         for(int i = down; i >= top; --i) System.out.print(matrix[i][left] + " ");
	         left++;
	         if(top > down || left > right) break;
	     }
	 }
```



Primitives passed by value in JavaScript
Objects passed by reference in JavaScript


Binary tree traversal: in-order, post-order, pre-order
in-order:
node.left, node, node.right
DFS:
void search(Node root) {
  if (root==null) return;
  visit(root);
  root.visited = true;
  foreach (Node n in root.adjacent) {
    if (n.visited== false) {
    search(n);
    }
  }
}
BFS:
void search(Node root) {
  Queue queue = new Queue();
  root.visited = true;visit(root);
  queue.enqueue(root); // Add to end of queue
  while (!queue.isEmpty()) {
    Node r = queue.dequeue();
    foreach (Node n in r.adjacent) {
      if (n.visited == false) {
        visit(n);
        n.visited = true;
        queue.enqueue(n);
      }
    }
  }
}
