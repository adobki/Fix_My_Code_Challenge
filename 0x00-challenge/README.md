# Fix-my-code-0
Applying the following fixes to the five packages in this folder completed the challenge:

### 0-fizzbuzz.py:
| Line Number | Applied Fix(es) |
|-------------|-----------------|
| `Line 20`   | Refactored if/elif block by moving the second statement (`if (i % 3) == 0 and (i % 5) == 0`) before the first one (`if (i % 3) == 0`).<br/>Previous arrangement nullified the second statement so that it was never processed at runtime. |

### 1-print_square.js:
| Line Number | Applied Fix(es) |
|-------------|-----------------|
| `Line 17`   | Removed number base specifier in parseInt() function. `size = parseInt(process.argv[2], 16)` **=>** `size = parseInt(process.argv[2])`.<br/>Previous setup caused the program to convert all given valid inputs to base 16/hex, which is why `10 == 16`. The second parameter in the function (`16`) should have been a `10`, or omitted altogether, to let the function detect the number system automatically, with decimal/base 10 as the default. |

### 2-sort.rb
| Line Number | Applied Fix(es) |
|-------------|-----------------|
| `Line 23`   | Removed decrement of `i` variable, the index passed to insert() method of the result array. `result.insert(i - 1, i_arg)` **=>** `result.insert(i, i_arg))`.<br/>Previous setup caused the program to always insert items before the expected index for the sorting operation, which led to a weirdly sorted array. |

### 3-user.py
| Line Number | Applied Fix(es) |
|-------------|-----------------|
| `Line 43`   | Renamed incorrectly named variable. `self._password ...` **=>** `self.__password ...`.<br/>Previous name was a typo that referenced `_password`, a private attribute, as opposed to `__password`, a protected attribute, which is the name/convention that was used in the rest of the class. |
| `Line 57`   | Changed formatting method used on string. `... .hexdigest().upper() ...` **=>** `... .hexdigest().lower() ...`.<br/>Previous method returned an uppercase string, whereas other call to the function used a lowercase string. Matching the case in this call to the case in the other one solved the mismatch problem. |

### 4-delete_dnodeint/delete_dnodeint_at_index.c
| Line Number | Applied Fix(es) |
|-------------|-----------------|
| `Line 46`   | Changed pointers/targetted variables. `(*head)->prev->prev = (*head)->prev` **=>** `(*head)->prev->next = (*head)->next`.<br/>Previous setup pointed to the wrong pointer in the wrong node, which could cause a node to remain in the list after it is deleted, leading to unexpected behaviour/app crash if an attempt is made to manipulate the deleted node subsequently. |
| `Line 47`   | Moved down two lines to `Line 49` so that it was run after the if statement. `free(*head);`<br/>Previous setup cleared the node from memory before the next node's previous pointer was set. This would have lead to problems if an attempt was made to travers the doubly linked list backwards/in reverse order. |
