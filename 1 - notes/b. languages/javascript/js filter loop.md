---
status: newBorn
related-links: 
created: 2025-06-09T17:30
updated: 2025-06-09T17:30
---
---

- used to filter things for which we need to provide a condition
- takes a callback as parameter inside where we define that condition
- returns all the elements of array that satisfies the condition
- have to store it

### basic code
```js
const myNums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

const newNums = myNums.filter( (num) => {
    return num > 4
} )

----- or -----

const myNums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

// here we didn't open scope so we don't have to use return keyword
const newNums = myNums.filter( (num) => return num > 4 )
```

### real world example
- considering we have a book website where the user is using filters to get the book he like so he can make a purchase. We have to create a filter that facilitates him for:
```js
// database
const books = [
    { title: 'Book One', genre: 'Fiction', publish: 1981, edition: 2004 },
    { title: 'Book Two', genre: 'Non-Fiction', publish: 1992, edition: 2008 },
    { title: 'Book Three', genre: 'History', publish: 1999, edition: 2007 },
    { title: 'Book Four', genre: 'Non-Fiction', publish: 1989, edition: 2010 },
    { title: 'Book Five', genre: 'Science', publish: 2009, edition: 2014 },
    { title: 'Book Six', genre: 'Fiction', publish: 1987, edition: 2010 },
    { title: 'Book Seven', genre: 'History', publish: 1986, edition: 1996 },
    { title: 'Book Eight', genre: 'Science', publish: 2011, edition: 2016 },
    { title: 'Book Nine', genre: 'Non-Fiction', publish: 1981, edition: 1989 },
];

// user wants book of genre history
let userBooks = books.filter((bk) => bk.genre === 'History')

// user wants book of history but not the ones published before 1995
userBooks = books.filter((bk) => {
    return bk.publish >= 1995 && bk.genre === "History"
})
console.log(userBooks);
```