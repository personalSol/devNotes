---
status: newBorn
related-links:
created: 1970-01-01T05:30
updated: 2026-01-15T21:14
---
---


> debouncing is we trying to not overwhealm the browser by writing a condition which if fulfills do saves in browser. 
> 
> ex: if we write a caption then if we attach an onclick lister on it to save the caption on local storage then it will create performane issue to overcome it instagram implemented debouncing. if a user writes captions then save it only after 300ms of when user stops writing. 
> other ex: when we resize a window then we debounce it to only resize the site view after 300ms of user not dragging the window
> - in lift when a person clicks a lift button 20 times then there is debounce there which says to only accept the request after the user is done clicking. it receives one request and not 20 (although here it should have something that stops sending request after first one as the extra or second request can't possible have any changes)

- **Problem:** Saving to `localStorage` or calling an API on **every** keystroke (like writing a caption) makes the app laggy and slow.
    
- **The Journey:**
    1. **The Trigger:** User types a letter.
    2. **The Delay:** A timer starts (e.g., 500ms).
    3. **The Reset:** If the user types another letter before the 500ms is up, the old timer is killed and a new one starts.
    4. **The Action:** Only after the user **stops** typing for a full 500ms does the "Save Draft" function actually run.