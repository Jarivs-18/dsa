# dsa

Subject: Data Structure and Algorithms
'''1] Write a program to implement Singly linked list with required member function
(constructor, insertfirst, insertpos, insertlast, deletefirst, deletelast, deletepo
class node:
 def __init__(self,value):
 self.data=value
 self.next=None
class sll:
 def __init__(self):
 self.head=None
 self.cnt=0
 def insertatfirst(self,value):
 newnode=node(value)
 newnode.next=self.head
 self.head=newnode
 self.cnt+=1
 def insertatpos(self,pos,value):
 newnode=node(value)
 cp=1
 if pos<=0 or pos>self.cnt+1:
 print("Invalid position")
 else:
 if pos==1:
 self.insertatfirst(value)
 elif pos==self.cnt+1:
 self.insertatlast(value)
 else:
 cur=self.head
 while (cp<pos-1):
 cur=cur.next
 cp+=1
 newnode.next=cur.next
 cur.next=newnode
 self.cnt+=1

 def insertatlast(self,value):
 newnode=node(value)
 if self.head is None:
 self.head=newnode
 self.cnt+=1
 else:
 cur=self.head
 while cur.next is not None:
 cur=cur.next
 cur.next=newnode
 self.cnt+=1
 def deleteatfirst(self): In [19]:
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 1/27
 if self.head is None:
 print("List is empty")
 else:
 temp=self.head
 self.head=self.head.next
 self.cnt-=1
 del temp
 def deleteatpos(self,pos):
 if pos<=0 or pos>self.cnt+1:
 print("Invalid Entry")
 else:
 if pos==1:
 self.deleteatfirst()
 elif pos==self.cnt:
 self.deleteatlast()
 else:
 cur=self.head
 cp=1
 while(cp<pos-1):
 cur=cur.next
 cp+=1
 temp=cur.next
 cur.next=temp.next
 self.cnt-=1
 del temp
 def deleteatlast(self):
 if self.head is None:
 print("List is empty")
 elif self.head.next is None:
 temp=self.head
 self.head=None
 del temp
 else:
 cur=self.head
 while cur.next.next is not None:
 cur=cur.next
 temp=cur.next
 cur.next=temp.next
 del temp
 self.cnt-=1
 def display(self):
 cur=self.head
 while cur is not None:
 print(f"{cur.data} ->",end='')
 cur=cur.next
 print()

s1=sll()
s1.insertatfirst(10)
s1.insertatfirst(20)
s1.insertatfirst(30)
s1.insertatpos(4,50)
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 2/27
print("List elements are:")
s1.display()
#s1.deleteatfirst()
s1.deleteatpos(3)
#s1.deleteatlast()
s1.display()
List elements are:
30 ->20 ->10 ->50 ->
30 ->20 ->50 ->
'''2] Write a program to implement Doubly linked list with required member function
(constructor, insertfirst, insertpos, insertlast, deletefirst, deletelast, deletepo
class node:
 def __init__(self,value):
 self.data=value
 self.next=None
 self.prev=None
class dll:
 def __init__(self):
 self.head=None
 self.cnt=0
 def insertatfirst(self,value):
 newnode=node(value)
 if self.head is None:
 self.head=newnode
 self.cnt+=1
 else:
 newnode.next=self.head
 self.head.prev=newnode
 self.head=newnode
 self.cnt+=1
 def insertatpos(self,pos,value):
 newnode=node(value)
 cp=1
 if pos<=0 or pos>self.cnt+1:
 print("Invalid position")
 else:
 if pos==1:
 self.insertatfirst(value)
 elif pos==self.cnt+1:
 self.insertatlast(value)
 else:
 cur=self.head
 while (cp<pos-1):
 cur=cur.next
 cp+=1
 newnode.prev=cur
 newnode.next=cur.next
 newnode.next.prev=newnode
 cur.next=newnode
 self.cnt+=1
In [24]:
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 3/27

 def insertatlast(self,value):
 newnode=node(value)
 if self.head is None:
 self.head=newnode
 self.cnt+=1
 else:
 cur=self.head
 while cur.next is not None:
 cur=cur.next
 cur.next=newnode
 newnode.prev=cur
 self.cnt+=1
 def deleteatfirst(self):
 if self.head is None:
 print("List is empty")
 elif self.head.next is None:
 temp=self.head
 self.head=None
 self.cnt-=1
 del temp
 else:
 temp=self.head
 self.head=self.head.next
 self.head.prev=None
 self.cnt-=1
 del temp
 def deleteatpos(self,pos):
 if pos<=0 or pos>self.cnt:
 print("Invalid Entry")
 else:
 if pos==1:
 self.deleteatfirst()
 elif pos==self.cnt:
 self.deleteatlast()
 else:
 cur=self.head
 cp=1
 while(cp<pos-1):
 cur=cur.next
 cp+=1
 temp=cur.next
 cur.next=temp.next
 temp.next.prev=cur
 self.cnt-=1
 del temp
 def deleteatlast(self):
 if self.head is None:
 print("List is empty")
 elif self.head.next is None:
 temp=self.head
 self.head=None
 self.cnt-=1
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 4/27
 del temp
 else:
 cur=self.head
 while cur.next is not None:
 cur=cur.next
 temp=cur
 cur.prev.next=None
 self.cnt-=1
 del temp
 def display(self):
 cur=self.head
 while cur is not None:
 print(f"{cur.data} ->",end='')
 cur=cur.next
 print()

s1=dll()
s1.insertatfirst(10)
s1.insertatfirst(20)
s1.insertatfirst(30)
s1.insertatpos(4,50)
print("List elements are:")
s1.display()
#s1.deleteatfirst()
s1.deleteatpos(3)
#s1.deleteatlast()
s1.display()
List elements are:
30 ->20 ->10 ->50 ->
30 ->20 ->50 ->
'''3]Write a program to implement Circular singly linked list with required data me
(constructor, insertfirst, insertpos, insertlast, deletefirst, deletelast, deletepo
class node:
 def __init__(self,value):
 self.data=value
 self.next=None
class sll:
 def __init__(self):
 self.head=None
 self.cnt=0
 def insertatfirst(self,value):
 newnode=node(value)
 if self.head is None:
 self.head=newnode
 newnode.next=newnode
 self.cnt+=1
 else:
 cur=self.head
 while cur.next is not self.head:
In [13]:
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 5/27
 cur=cur.next
 newnode.next=self.head
 cur.next=newnode
 self.head=newnode
 self.cnt+=1
 def insertatpos(self,pos,value):
 newnode=node(value)
 cp=1
 if pos<=0 or pos>self.cnt+1:
 print("Invalid position")
 else:
 if pos==1:
 self.insertatfirst(value)
 elif pos==self.cnt+1:
 self.insertatlast(value)
 else:
 cur=self.head
 while (cp<pos-1):
 cur=cur.next
 cp+=1
 newnode.next=cur.next
 cur.next=newnode
 self.cnt+=1

 def insertatlast(self,value):
 newnode=node(value)
 if self.head is None:
 self.head=newnode
 newnode.next=newnode
 else:
 cur=self.head
 while cur.next is not self.head:
 cur=cur.next
 newnode.next=self.head
 cur.next=newnode
 self.cnt+=1
 def deleteatfirst(self):
 if self.head is None:
 print("List is empty")
 elif self.head.next is self.head:
 temp=self.head
 self.head=None
 self.cnt-=1
 else:
 temp=self.head
 cur=self.head
 while cur.next is not self.head:
 cur=cur.next
 cur.next=temp.next
 self.head=temp.next
 self.cnt-=1
 del temp
 def deleteatpos(self,pos):
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 6/27
 if pos<=0 or pos>self.cnt+1:
 print("Invalid Entry")
 else:
 if pos==1:
 self.deleteatfirst()
 elif pos==self.cnt:
 self.deleteatlast()
 else:
 cur=self.head
 cp=1
 while(cp<pos-1):
 cur=cur.next
 cp+=1
 temp=cur.next
 cur.next=temp.next
 self.cnt-=1
 del temp
 def deleteatlast(self):
 if self.head is None:
 print("List is empty")
 elif self.head.next is self.head:
 temp=self.head
 self.head=None
 del temp
 else:
 cur=self.head
 while cur.next.next is not self.head:
 cur=cur.next
 temp=cur.next
 cur.next=temp.next
 del temp
 self.cnt-=1
 def display(self):
 cur=self.head
 while cur.next is not self.head:
 print(f"{cur.data} ->",end='')
 cur=cur.next
 print(f"{cur.data}")

s1=sll()
s1.insertatfirst(10)
s1.insertatfirst(20)
s1.insertatfirst(30)
#s1.insertatpos(4,50)
print("List elements are:")
s1.display()
#s1.deleteatfirst()
#s1.deleteatpos(3)
#s1.deleteatlast()
#s1.display()
List elements are:
30 ->20 ->10
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 7/27
'''4] Write a program to reverse Singly Linked List, Doubly Linked List'''
class slnode:
 def __init__(self,value):
 self.data=value
 self.next=None
class sll:
 def __init__(self):
 self.head=None
 self.cnt=0
 def insertatfirst(self,value):
 newnode=node(value)
 newnode.next=self.head
 self.head=newnode
 self.cnt+=1
 def display(self):
 cur=self.head
 while cur is not None:
 print(f"{cur.data} ->",end='')
 cur=cur.next
 print()
 def reverse(self):
 cur=self.head
 s1=[]
 while cur is not None:
 s1.append(cur.data)
 cur=cur.next
 s2=s1[::-1]
 for i in s2:
 print(i,"->",end='')
class dlnode:
 def __init__(self,value):
 self.data=value
 self.next=None
 self.prev=None
class dll:
 def __init__(self):
 self.head=None
 self.cnt=0
 def insertatfirst(self,value):
 newnode=dlnode(value)
 if self.head is None:
 self.head=newnode
 self.cnt+=1
 else:
 newnode.next=self.head
 self.head.prev=newnode
 self.head=newnode In [26]:
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 8/27
 self.cnt+=1
 def display(self):
 cur=self.head
 while cur is not None:
 print(f"{cur.data} ->",end='')
 cur=cur.next
 print()
 def reverse(self):
 cur=self.head
 while cur.next is not None:
 cur=cur.next
 n=self.cnt
 for i in range(n,0,-1):
 print(f"{cur.data} ->",end='')
 cur=cur.prev

s1=sll()
s1.insertatfirst(10)
s1.insertatfirst(20)
s1.insertatfirst(30)
print("Singly List elements are:")
s1.display()
print("Reversed")
s1.reverse()

s2=dll()
s2.insertatfirst(40)
s2.insertatfirst(50)
s2.insertatfirst(60)
print("Doubly List elements are:")
s2.display()
print("Reversed")
s2.reverse()
Singly List elements are:
30 ->20 ->10 ->
Reversed
10 ->20 ->30 ->Doubly List elements are:
60 ->50 ->40 ->
Reversed
40 ->50 ->60 ->
'''5] Write a program to implement STACK using Array with PUSH, POP operations'''
class Stack:
 def __init__(self,size):
 self.top = -1
 self.size = size
 self.data = [None] * size
 def push(self,val):
 if self.top == self.size - 1:
 print("Stack is Full")
In [20]:
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 9/27
 return
 else:
 self.top += 1
 self.data[self.top] = val
 def pop(self):
 if self.top == -1:
 print("Stack is Empty")
 else:
 temp = self.data[self.top]
 self.top -= 1
 print("Popped Element:",temp)
 def peek(self):
 if self.top == -1:
 print("Stack is Empty")
 else:
 temp = self.data[self.top]
 print("\nPeeked Element:",temp)

 def display(self):
 print("Stack Elements:")
 self.cnt = self.top
 while self.cnt > -1:
 print(self.data[self.cnt],"<-",end='')
 self.cnt -= 1
S1 = Stack(5)
S1.push(10)
S1.push(20)
S1.push(30)
S1.push(40)
S1.push(50)
S1.display()
S1.peek()
S1.pop()
S1.pop()
S1.display()
Stack Elements:
50 <-40 <-30 <-20 <-10 <-
Peeked Element: 50
Popped Element: 50
Popped Element: 40
Stack Elements:
30 <-20 <-10 <-
'''6] Write a program to implement Stack using Linked List with PUSH, POP,PEEK and
class Node:
 def __init__(self,val):
 self.data = val
 self.next = None

class Stack:
 def __init__(self,size):
 self.size = size In [11]:
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 10/27
 self.top = None
 self.cnt = 0

 def push(self,val):
 if self.cnt == self.size:
 print("Stack is full")
 return
 else:
 NN = Node(val)
 NN.next = self.top
 self.top = NN
 self.cnt += 1
 def peek(self):
 if self.top == None:
 print("Stack is Empty")
 return
 else:
 val = self.top.data
 print("\nPeeked Element: ", val)
 def pop(self):
 if self.top == None:
 print("Stack is Empty")
 return
 else:
 val = self.top.data
 self.top = self.top.next
 self.cnt -= 1
 print("Popped Element:",val)
 def display(self):
 cnt = self.top
 if cnt == None:
 print("Stack is empty")
 return
 else:
 print("Stack elements:")
 while cnt != None:
 print(cnt.data," <- ",end='')
 cnt = cnt.next

stk = Stack(5)
stk.push(10)
stk.push(20)
stk.push(30)
stk.push(40)
stk.display()
stk.peek()
stk.pop()
stk.push(70)
stk.display()
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 11/27
Stack elements:
40 <- 30 <- 20 <- 10 <-
Peeked Element: 40
Popped Element: 40
Stack elements:
70 <- 30 <- 20 <- 10 <-
'''7] Write a application of stack to Check for balanced parentheses.
Write a program to Reverse a string using stack'''# Program to check balanced paren
def is_balanced(expression):
 stack = []
 pairs = {')': '(', '}': '{', ']': '['}
 for ch in expression:
 if ch in "({[":
 stack.append(ch) # push
 elif ch in ")}]":
 if not stack: # empty stack
 return False
 top = stack.pop() # pop
 if pairs[ch] != top:
 return False
 return len(stack) == 0
exp ="(a+b)*[c-d]/f*g"
if is_balanced(exp):
 print("Balanced Expression")
else:
 print("Not Balanced")
def reverse_string(s):
 stack = []
 for ch in s:
 stack.append(ch)
 rev = ""
 # Pop characters
 while stack:
 rev += stack.pop()
 return rev
s ="IICMR"
print("Reversed String:", reverse_string(s))
Balanced Expression
Reversed String: RMCII
'''Q.8 - Write a program to implement
1. Linear Queue using list'''
class Node:
 def __init__(self, val):
 self.data = val
 self.next = None
 In [3]: In [4]:
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 12/27
class CQ:
 def __init__(self, size):
 self.front = None
 self.rear = None
 self.size = size
 self.cnt = 0
 self.deleted_items = []
 def enqueue(self, val):
 NewNode =Node(val)
 if self.cnt == self.size:
 print("Queue is full")
 return

 if self.front is None:
 self.front = NewNode
 self.rear = NewNode
 NewNode.next = self.front
 else:
 self.rear.next = NewNode
 NewNode.next = self.front
 self.rear = NewNode
 self.cnt += 1
 def dequeue(self):
 if self.front is None:
 print("Queue is empty")
 return
 if self.front == self.rear:
 temp = self.front.data
 self.front = None
 self.rear = None
 else:
 temp = self.front.data
 self.front = self.front.next
 self.rear.next = self.front

 self.deleted_items.append(temp)
 self.cnt -= 1
 def display(self):
 if self.front is None:
 print("Queue is empty")
 return
 curr = self.front
 while curr.next != self.front:
 print(curr.data, end=" -> ")
 curr = curr.next
 print(curr.data)
c = CQ(5)
c.enqueue(10)
c.enqueue(20)
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 13/27
c.enqueue(30)
c.enqueue(40)
c.enqueue(50)
print("\nQueue Elements:")
c.display()
c.dequeue()
c.dequeue()
print("Deleted Elements:")
print(c.deleted_items)
print("After Deleting QUEUE Elements:")
c.display()
print("Newly inserted Queue Elements:")
c.enqueue(60)
c.enqueue(70)
c.enqueue(80)
c.display()
Queue Elements:
10 -> 20 -> 30 -> 40 -> 50
Deleted Elements:
[10, 20]
After Deleting QUEUE Elements:
30 -> 40 -> 50
Newly inserted Queue Elements:
Queue is full
30 -> 40 -> 50 -> 60 -> 70
'''Q.8 - Write a program to implement
2]Circular Queue using list'''
class Node:
 def __init__(self,val):
 self.next = None
 self.data = val

class CQ:
 def __init__(self,size):
 self.front = None
 self.rear = None
 self.size = size
 self.cnt = 0

 def enqueue(self,val):
 NewNode =Node(val)
 if self.cnt == self.size:
 print("Queue is full")
 return
 elif self.front is None:
 self.front = NewNode
 self.rear = NewNode
 NewNode.next = self.front
 else:
 self.rear.next = NewNode
 NewNode.next = self.front
 self.rear = NewNode
 self.cnt += 1
In [7]:
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 14/27

 def dequeue(self):
 if self.front is None:
 print("Queue is empty")
 return
 elif self.front == self.rear:
 temp = self.front.data
 self.front = None
 self.rear = None
 del temp
 else:
 temp = self.front.data
 self.front = self.front.next
 self.rear.next = self.front
 del temp
 self.cnt -= 1
 def display(self):
 curr = self.front
 while curr.next != self.front:
 print(curr.data, end = "-> ")
 curr = curr.next
 print(curr.data)

c = CQ(5)
c.enqueue(10)
c.enqueue(20)
c.enqueue(30)
c.enqueue(40)
c.enqueue(50)
print("QUEUE Elements: ")
c.display()
c.dequeue()
print("After Deleting QUEUE Elements: ")
c.display()
QUEUE Elements:
10-> 20-> 30-> 40-> 50
After Deleting QUEUE Elements:
20-> 30-> 40-> 50
'''9] Write a program to Reverse stack using queue'''
from queue import Queue
def reverse_stack(stack):
 q = Queue()
 while stack:
 q.put(stack.pop())
 while not q.empty():
 stack.append(q.get())
 return stack
stack = [1,11,12,7]
print("Original Stack:", stack)
reversed_stack = reverse_stack(stack)
print("Reversed Stack:", reversed_stack)
In [2]:
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 15/27
Original Stack: [1, 11, 12, 7]
Reversed Stack: [7, 12, 11, 1]
'''10] Write a program to implement binary search tree with its operations '''
class Node:
 def __init__(self,val):
 self.lchild=None
 self.data=val
 self.rchild=None
class Btree:
 def __init__(self):
 self.root=None
 def insert(self,val):
 temp=Node(val)
 trv=self.root
 if self.root is None:
 self.root=temp
 return
 else:
 while True:
 if(val > trv.data):
 if trv.rchild is None:
 trv.rchild=temp
 return
 else:
 trv=trv.rchild
 else:
 if trv.lchild is None:
 trv.lchild=temp
 return
 else:
 trv=trv.lchild

 def search(self,key):
 trv=self.root
 while True:
 if trv is None:
 return False
 if trv.data==key:
 return True
 if trv.data<key:
 trv=trv.rchild
 else:
 trv=trv.lchild

 def searchR(self, root, key):
 if root is None:
 return False
 elif key < root.data:
 return self.search(root.lchild,key)
 elif key > root.data:
 return self.search(root.rchild,key)
 else:
 if root.data==key:
 return True In [4]:
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 16/27
 else:
 return False

 # Print Inorder
 def inorder(self,rt):
 if rt is not None:
 self.inorder(rt.lchild)
 print(rt.data,end=" ")
 self.inorder(rt.rchild)
 # Print preorder
 def preorder(self,rt):
 if rt is not None:
 print(rt.data,end=" ")
 self.preorder(rt.lchild)
 self.preorder(rt.rchild)
 # Print postorder
 def postorder(self,rt):
 if rt is not None:
 self.postorder(rt.lchild)
 self.postorder(rt.rchild)
 print(rt.data,end=" ")
 # Inorder Traversal
 def inorder_traversal(self):
 stack = []
 current = self.root
 result = []
 while current or stack:
 while current:
 stack.append(current)
 current = current.lchild
 current = stack.pop()
 result.append(current.data)
 current = current.rchild
 return result
 # preorder Traversal
 def preorder_traversal(self):
 if not self.root:
 return []
 stack, result = [self.root], []
 while stack:
 node = stack.pop()
 result.append(node.data)
 # Push right child first so that left is processed first
 if node.rchild:
 stack.append(node.rchild)
 if node.lchild:
 stack.append(node.lchild)
 return result
 # postorder Traversal
 def post_order_traversal(self):
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 17/27
 if self.root is None:
 return []
 stack1 = []
 stack2 = []
 stack1.append(self.root)
 while stack1:
 node = stack1.pop()
 stack2.append(node)
 if node.lchild:
 stack1.append(node.lchild)
 if node.rchild:
 stack1.append(node.rchild)
 result = []
 while stack2:
 node = stack2.pop()
 result.append(node.data)
 return result

bst=Btree()
bst.insert(10)
bst.insert(5)
bst.insert(20)
bst.insert(50)
bst.insert(30)
bst.insert(40)
bst.insert(35)
print("Inorder:")
bst.inorder(bst.root)
print("\nPreorder:")
bst.preorder(bst.root)
print("\nPostorder:")
bst.postorder(bst.root)
print("\nSearch for 10 in the BST:", bst.search(10))
Inorder:
5 10 20 30 35 40 50
Preorder:
10 5 20 50 30 40 35
Postorder:
5 35 40 30 50 20 10
Search for 10 in the BST: True
'''11] Write a program to implement AVL Tree.'''
class Node:
 def __init__(self, value):
 self.value = value
 self.left = None
 self.right = None
 self.height = 1
In [7]:
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 18/27
class AVLTree:
 def __init__(self):
 self.root = None
 def height(self, node):
 if not node:
 return 0
 return node.height
 def balance(self, node):
 if not node:
 return 0
 return self.height(node.left) - self.height(node.right)
 def insert(self, root, value):
 if not root:
 return Node(value)
 elif value < root.value:
 root.left = self.insert(root.left, value)
 else:
 root.right = self.insert(root.right, value)
 root.height = 1 + max(self.height(root.left), self.height(root.right))
 balance = self.balance(root)
 # Left rotation
 if balance > 1 and value < root.left.value:
 return self.right_rotate(root)
 # Right rotation
 if balance < -1 and value > root.right.value:
 return self.left_rotate(root)
 # Left-Right rotation
 if balance > 1 and value > root.left.value:
 root.left = self.left_rotate(root.left)
 return self.right_rotate(root)
 # Right-Left rotation
 if balance < -1 and value < root.right.value:
 root.right = self.right_rotate(root.right)
 return self.left_rotate(root)
 return root

 def delete(self, root, value):
 if not root:
 return root
 if value < root.value:
 root.left = self.delete(root.left, value)
 elif value > root.value:
 root.right = self.delete(root.right, value)
 else:
 if not root.left:
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 19/27
 temp = root.right
 root = None
 return temp
 elif not root.right:
 temp = root.left
 root = None
 return temp
 temp = self.min_value_node(root.right)
 root.value = temp.value
 root.right = self.delete(root.right, temp.value)
 if not root:
 return root
 root.height = 1 + max(self.height(root.left), self.height(root.right))
 balance = self.balance(root)
 # Left rotation
 if balance > 1 and self.balance(root.left) >= 0:
 return self.right_rotate(root)
 # Right rotation
 if balance < -1 and self.balance(root.right) <= 0:
 return self.left_rotate(root)
 # Left-Right rotation
 if balance > 1 and self.balance(root.left) < 0:
 root.left = self.left_rotate(root.left)
 return self.right_rotate(root)
 # Right-Left rotation
 if balance < -1 and self.balance(root.right) > 0:
 root.right = self.right_rotate(root.right)
 return self.left_rotate(root)
 return root
 def left_rotate(self, z):
 y = z.right
 T2 = y.left
 y.left = z
 z.right = T2
 z.height = 1 + max(self.height(z.left), self.height(z.right))
 y.height = 1 + max(self.height(y.left), self.height(y.right))
 return y
 def right_rotate(self, z):
 y = z.left
 T3 = y.right
 y.right = z
 z.left = T3
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 20/27
 z.height = 1 + max(self.height(z.left), self.height(z.right))
 y.height = 1 + max(self.height(y.left), self.height(y.right))
 return y
 def min_value_node(self, root):
 current = root
 while current.left:
 current = current.left
 return current
 def search(self, root, value):
 if not root or root.value == value:
 return root
 if root.value < value:
 return self.search(root.right, value)
 return self.search(root.left, value)
 def insert_value(self, value):
 self.root = self.insert(self.root, value)
 def delete_value(self, value):
 self.root = self.delete(self.root, value)
 def search_value(self, value):
 return self.search(self.root, value)
 # In-order traversal to print the tree
 def inorder_traversal(self,root):
 if root:
 self.inorder_traversal(root.left)
 print(root.value,end=' '),
 self.inorder_traversal(root.right)

tree = AVLTree()
tree.insert_value(10)
tree.insert_value(20)
tree.insert_value(30)
tree.insert_value(60)
tree.insert_value(45)
print("Tree after insertion:")
tree.inorder_traversal(tree.root)
print()
result = tree.search_value(70)
if result:
 print("Node found")
else:
 print("Node not found")
Tree after insertion:
10 20 30 45 60
Node not found
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 21/27
'''12] Write a program to implement Graph
1. Adjacency List '''
def adjacency_list_dictionary(v, edges):
 adjacency_list = {}
 for i in range(v):
 adjacency_list[i] = []
 for edge in edges:
 vertex1, vertex2 = edge
 adjacency_list[vertex1].append(vertex2)
 print("Adjacency List:")
 for vertex, neighbours in adjacency_list.items():
 print(f"{vertex} -> {' '.join(map(str, neighbours))}")
vertex = 4
edges = [[0, 1], [1, 2], [2, 3],[1,3],[3,0]]
adjacency_list_dictionary(vertex, edges)
Adjacency List:
0 -> 1
1 -> 2 3
2 -> 3
3 -> 0
'''12] Write a program to implement Graph
2. Adjacency Matrix'''
def adjacency_matrix(vertex,edges):
 matrix = [0] * vertex
 for r in range(0,vertex):
 matrix[r] = [0] * vertex
 for eg in edges:
 u,v = eg
 matrix[u][v] = 1
 matrix[v][u] = 1
 return matrix

vertex = 4
edges = [(0, 1), (1, 2), (2, 3),(1,3),(3,0)]
adjacency_matrix = adjacency_matrix(vertex,edges)
print("Adjacency Matrix:")
for row in adjacency_matrix:
 print(row)
Adjacency Matrix:
[0, 1, 0, 1]
[1, 0, 1, 1]
[0, 1, 0, 1]
[1, 1, 1, 0]
In [8]: In [9]:
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 22/27
'''13] Write a Program to find the element in an array using
1.Binary Search'''
def binary_search(arr,x):
 low = 0
 high = len(arr)-1
 while low <= high:
 mid = (high + low) // 2
 if arr[mid] < x:
 low = mid + 1
 elif arr[mid] > x:
 high = mid - 1
 else:
 return mid
 return -1
arr = [2,3,4,10,40]
x = 40
result = binary_search(arr,x)
print("Original Array:",arr)
if result != -1:
 print("Element present at index:",str(result))
else:
 print("Element not present in array")
Original Array: [2, 3, 4, 10, 40]
Element present at index: 4
'''13] Write a Program to find the element in an array using
2.Linear Search'''
def linear_search(arr, key):
 for i in range(len(arr)):
 if arr[i] == key:
 return i
 return -1
def binary_search(arr, key):
 left = 0
 right = len(arr) - 1
 while left <= right:
 mid = (left + right) // 2
 if arr[mid] == key:
 return mid
 elif key < arr[mid]:
 right = mid - 1
 else:
 left = mid + 1
 return -1
arr = [10, 20, 30, 40, 50, 60]
key = 60
print("Array:", arr)
In [10]: In [11]:
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 23/27
# Linear Search Call
ls = linear_search(arr, key)
print("Linear Search:")
print("Element found at index" if ls != -1 else "Element not found.", ls)
Array: [10, 20, 30, 40, 50, 60]
Linear Search:
Element found at index 5
'''14] Write a program to implement sorting using Divide and Conquer strategy
1. Quick sort 2.Merge sort'''
def partition(arr,low,high):
 pivot= arr[high]
 i=low-1
 for j in range(low,high):
 if arr[j]<=pivot:
 i+=1
 arr[i],arr[j]=arr[j],arr[i]
 arr[i+1],arr[high]=arr[high],arr[i+1]
 return i+1
def quick_sort(arr,low,high):
 if low< high:
 p = partition(arr,low,high)
 quick_sort(arr,low,p -1)
 quick_sort(arr,p+1,high)

def merge_sort(arr):
 if len(arr)<=1:
 return arr
 mid=len(arr)//2
 left=merge_sort(arr[:mid])
 right=merge_sort(arr[mid:])
 return merge(left,right)
def merge(left,right):
 merged=[]
 i=j=0
 while i<len(left) and j<len(right):
 if left[i]<=right[j]:
 merged.append(left[i])
 i+=1
 else:
 merged.append(right[j])
 j+=1
 merged.extend(left[i:])
 merged.extend(right[j:])
 return merged
arr=[24,32,25,46,87,86]
print("Original array: ",arr)
quick_sort(arr,0,len(arr)-1)
print("Array after quick sort: ",arr)
print("Array after merge: ",merge_sort(arr))
In [17]:
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 24/27
Original array: [24, 32, 25, 46, 87, 86]
Array after quick sort: [24, 25, 32, 46, 86, 87]
Array after merge: [24, 25, 32, 46, 86, 87]
Subject: Python Programming
'''1] Write Python Program to count the Total Number of Vowels, Consonants and
Blanksin a String.Create Stack using list and implement necessary operation'''
# Simple Stack using list
class Stack:
 def __init__(self):
 self.items = []
 def push(self, x):
 self.items.append(x)
 def pop(self):
 return self.items.pop()
 def peek(self):
 return self.items[-1] if self.items else None
 def is_empty(self):
 return len(self.items) == 0
# Input string and stack
s = "HelloO AIWorld"
stack = Stack()
for ch in s:
 stack.push(ch)
# Counters
vowels = consonants = blanks = 0
# Pop and count
while not stack.is_empty():
 ch = stack.pop()
 if ch==' ': blanks+=1
 elif ch.lower() in 'aeiou': vowels += 1
 else:
 consonants += 1
print("Vowels:", vowels)
print("Consonants:", consonants)
print("Blanks:", blanks)
Vowels: 6
Consonants: 7
Blanks: 1
'''2] Write a program to print following pattern
A 4444 1
B C 333 0 1
C D E 22 1 0 1
D E F G 1 0 1 0 1 '''
a=int(input("Enter no.of rows: "))
ch='A' In [30]: In [3]:
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 25/27
for row in range(0,a):
 for col in range(0,row):
 print(ch,end=' ')
 ch=chr(ord(ch)+1)
 print()

print()
a=int(input("Enter no.of rows: "))
for row in range(a,0,-1):
 for col in range(row,0,-1):
 print(row,end=' ')
 print()
print()
a=int(input("Enter no.of rows: "))
for row in range(0,a):
 for k in range(a-row-1):
 print(' ',end='')
 for col in range(0,row+1):
 if (col+row)%2==0:
 print("1",end=' ')
 else:
 print("0",end=' ')
 print()
A
B C
D E F
G H I J
4 4 4 4
3 3 3
2 2
1
 1
 0 1
 1 0 1
0 1 0 1
1 0 1 0 1
'''3] Write a program which generates account number using random function'''
import random
acc_no = random.randint(100000000000, 999999999999)
print("Generated Account Number:", acc_no)
Generated Account Number: 704852390403
'''4] Write Python Program to Conduct a Linear Search for a Given Key Number in the
numbers = [10, 20, 30, 40, 50, 60, 70, 80, 90, 99]
num = int(input("Enter the number to search: "))
found = False
for i in numbers:
 if i == num:
In [4]: In [ ]:
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 26/27
 found = True
 break
if found:
 print("The number is found")
else:
 print("Number is not found")
'''5] Write Python Program to Add Two Matrices'''
import numpy as np
A = np.array([[1, 2, 3],
 [4, 5, 6],
 [7, 8, 9]])
B = np.array([[1, 2, 3],
 [4, 5, 6],
 [7, 8, 9]])
result = A + B
print("Matrix Addition:")
print(result)
Matrix Addition:
[[ 2 4 6]
[ 8 10 12]
[14 16 18]]
pip install pymongo
Requirement already satisfied: pymongo in c:\users\manis\appdata\local\programs\pyth
on\python314\lib\site-packages (4.15.5)
Requirement already satisfied: dnspython<3.0.0,>=1.16.0 in c:\users\manis\appdata\lo
cal\programs\python\python314\lib\site-packages (from pymongo) (2.8.0)
Note: you may need to restart the kernel to use updated packages.
[notice] A new release of pip is available: 25.2 -> 25.3
[notice] To update, run: python.exe -m pip install --upgrade pip
In [5]: In [4]: In [ ]:
12/9/25, 8:25 PM rollno_66
file:///C:/Users/manis/Downloads/rollno_66.html 27/27
