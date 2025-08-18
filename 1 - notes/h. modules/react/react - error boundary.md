---
status: newBorn
related-links: 
created: 2025-07-16T15:20
updated: 2025-07-18T21:59
---
---

- error boundary is basically a bounday which stops error from propogating and crashing the whole app
- in this we wrap out component which we know might probably crash into a class component `ErrorBoundary`.
- ex:
```jsx
<ErrorBoundary>
	<ChildComponent>
</ErrorBoundary>
```
- This component contains logic to show a fallback component if the child component crashes
- or otherwise it renders the component normally
- pros: 
	- prevents the whole app from crashing
- it's code can be treated as blackbox and just be copy pasted
	- snippet: [[snp react error boundary]]
![[Screenshot_2024-10-06_at_7.44.33_PM.webp]]
- i actually don't understand this photo's text but copied it regardless

