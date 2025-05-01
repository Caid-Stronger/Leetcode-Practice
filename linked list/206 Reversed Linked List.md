![image](https://github.com/user-attachments/assets/749506ee-228b-4e53-abf8-900103490c55)

Python Code -- Two pinter
```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        current = head 
        previous = None 

        while current:
            temporary = current.next # 保存一下 cur的下一个节点，因为接下来要改变cur->next
            current.next = previous #反转
            # 更新指针
            previous = current 
            current= temporary
        return previous

```

```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        return self.reverse(head, None) 
    
    def reverse(self, current:ListNode, pre:ListNode) ->ListNode: 
        if current == None:
            return pre 
        temporary = current.next 
        current.next = pre 
        return self.reverse(temporary, current)
```

用 `current` 遍历链表，用 `previous` 保存反转后的链表头。

每次将当前节点的 `next` 指向前一个节点，实现局部反转。

然后更新两个指针继续处理下一个节点

每一步都就地反转当前节点的方向，同时用 `temporary` 保存原来的 `next`，防止链表断开。 

Use `current` to traverse the linked list and `previous` to store the head of the reversed list.

At each step, set the `next pointer of the current node` to point to `the previous node`

Then, update both pointers to move on to the next node.

Each step reverses the direction of the current node in place, while `temporary` preserves the original next node to prevent breaking the list.
