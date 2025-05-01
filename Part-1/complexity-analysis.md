# `Algorithm Analysis`

## Algorithm 1 : `Insert at the beginning of a dynamic array.`

```javaScript
  function insert (index, element) {
		if (index < 0 || index > this.length) {
			throw new Error('Index out of bounds');
		}

		if (this.length === this.capacity) {
			this.#grow();
		}

		for (let i = this.length; i > index; i--) {
			this.array[i] = this.array[i - 1];
		}
		this.array[index] = element;
		this.length++;
	}
```

### 1. Input Output Mapping

- Input : an `index` number where the element is to be inserted and the `value` to be inserted.
- Output : None.

### 2. Step by Step Cost breakdown

- #### check if the index is valid - _O(1)_
- #### check if the array is full - _O(1)_
- #### shift elements to the right - _O(n)_
- #### insert the element - _O(1)_
- #### increment the length - _O(1)_

### Total cost is dominated by the loop, which is _O(n)_.
