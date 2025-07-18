---
status: newBorn
related-links: 
created: 2025-05-28T03:51
updated: 2025-07-18T22:32
---
---


We do import and export in JS files.

- Import basic
	- to import we use require keyword and inside require, we give the file name `also path if it’s not in ssame folder`
        - As we can see we have imported commander package and fs package using the keyword `require` . Using quotes is a must here.
        - We can attach or omit .js at the end of fs or any other module we import as NodeJs attachs it.
        - By importing these packages, we can use whatever was exported by that file.
    
        ```java
        const fs = require('fs');
        const { Command } = require('commander');
        const program = new Command();
        
        program
          .name('counter')
          .description('CLI to do file based tasks')
          .version('0.8.0');
        
        program.command('count')
          .description('Count the number of lines in a file')
          .argument('<file>', 'file to count')
          .action((file) => {
            fs.readFile(file, 'utf8', (err, data) => {
              if (err) {
                console.log(err);
              } else {
                const lines = data.split(' ').length;
                console.log(data.split(' '));
                console.log(`There are ${lines} lines in ${file}`);
              }
            });
          });
        
        program.parse();
        ```
        
- Export
    
    We use `module.exports` to pass the value we want to be exported to other files which import that file.
    
    - we can export functions like this
        ![[general code copy block note#export in cjs]]![[general code copy block note#to export multiple things in cjs]]
    
- code example doing import and export of a small file

File which will import another — test2.js

```java
    const imp = require('./test.js');
    
    console.log(imp.b);
    console.log(imp.a);
```

File which will be exported — test.js

```js
    let a = 456;
    
    let b = 2387389;
    
    module.exports = {first: a,second: b};
```

