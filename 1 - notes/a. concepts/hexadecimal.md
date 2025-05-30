---
status: newBorn
related-links: 
created: 2025-05-25T08:49
updated: 2025-05-27T16:42
---
---

<aside> 📌 All about hex

</aside>

![[Pasted image 20250525085114.png||300]]
- in short we call it hex
- a hext value generally starts with `0x` zero x
- `1 character = 4 bits`
    - Means after converting an integer to binary. It makes a group of 4 binary number from left. Each group represents 1 number of hexadecimal.
- A single hex character can be any of the 16 possible values: `0-9` and `A-F`.
- the reason we have A instead of 10 is that if we write 10 then we wouldn't know if 10 is the 10th digit of 2 different digits. 
	- this prevents us from confusion that 11 is B or two separate 1's 



### code

- Array to Hex
    ```jsx
    function arrayToHex(byteArray) {
      let hexString = '';
      for (let i = 0; i < byteArray.length; i++) {
        hexString += byteArray[i].toString(16).padStart(2, '0');
      }
      return hexString;
    }
    
    // Example usage:
    const byteArray = new Uint8Array([72, 101, 108, 108, 111]); // Corresponds to "Hello"
    const hexString = arrayToHex(byteArray);
    console.log(hexString); // Output: "48656c6c6f"
    
    ```
- hex to array
    
    ```jsx
    function hexToArray(hexString) {
      const byteArray = new Uint8Array(hexString.length / 2);
      for (let i = 0; i < byteArray.length; i++) {
        byteArray[i] = parseInt(hexString.substr(i * 2, 2), 16);
      }
      return byteArray;
    }
    
    // Example usage:
    const hex = "48656c6c6f";
    const byteArrayFromHex = hexToArray(hex);
    console.log(byteArrayFromHex); // Output: Uint8Array(5) [72, 101, 108, 108, 111]
    
    ```

Ref- [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt)

