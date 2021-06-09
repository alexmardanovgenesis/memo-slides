![](https://i.ytimg.com/vi/3cYtqrNUiVw/maxresdefault.jpg)

---

![](https://i.pinimg.com/originals/d6/a7/4a/d6a74af853efada6dbf21bdbdac913e8.jpg)

https://codesandbox.io/s/reactmemo-do2gv

---

![](https://cdn.devdojo.com/posts/images/April2021/what-is-usecallback-hook-in-react-5f3cb7ca9584ef298dc17325.jpg)

https://codesandbox.io/s/reactusecallback-ypuel

---

## When to use useCallback

- A functional component wrapped inside React.memo() accepts a function object prop
- When the function object is a dependency to other hooks, e.g. useEffect(..., [callback])
- When the function has some internal state, e.g. when the function is debounced or throttled.

---

![](https://i0.wp.com/everyday.codes/wp-content/uploads/2020/02/a.jpg?fit=1200%2C630&ssl=1)

https://codesandbox.io/s/usememo-ydu50

https://codesandbox.io/s/usememo-2-fkulb

---

> Users enjoy fast and responsive user interfaces (UI). A UI response delay of fewer than 100 milliseconds feels instant to the user but a delay between 100 and 300 milliseconds is already perceptible.

---

![](https://dmitripavlutin.com/static/c07d2ce4ede6301197b9605a75ae9b4e/7c84e/when-to-use-react-memo-infographic.webp)

---

> The more often the component renders with the same props, the heavier and the more computationally expensive the output is, the more chances are that component needs to be wrapped in React.memo().

---

> If the component isn’t heavy and usually renders with different props, most likely you don’t need React.memo().

> Use the following rule of thumb: don’t use memoization if you can’t quantify the performance gains.

> Performance-related changes applied incorrectly can even harm performance. Use React.memo() wisely.

---

## Rules of optimization

- Don't
- Don't... yet
- Profile before optimizing!

**Performance optimizations are not free. They ALWAYS come with a cost but do NOT always come with a benefit to offset that cost.**

---

## Some statistics...

---

![](https://miro.medium.com/max/2400/1*k28DMvf9-wlr8I1bZX_aqw.png)

**In conclusion, for complexity n=1, it is always faster to not use useMemo as the overHead is always more expensive than the performance gain.**

---

![](https://miro.medium.com/max/2400/1*VhhokD97WBh3vk7ZBnSXdA.png)

**In conclusion with a complexity of 100, the initial render is significantly slower, while the subsequent re-renders are quite similar and at best slightly faster. At this point, useMemo does not seem interesting yet.**

---

![](https://miro.medium.com/max/2400/1*9fNFqMwfSA2sXpm7PCl_8Q.png)

**In conclusion, with a complexity of 1000, we can see a bigger performance loss during the initial render (183%), however, subsequent renders are about 37% faster. Whether this is already interesting or not will highly depend on your use case. A 183% performance loss during the initial render is a tough sell, but might be justifiable in case of a lot of re-renders in the component.**

---

![](https://miro.medium.com/max/2400/1*N5HynmPMLilPskclqm0fyw.png)

**In conclusion, the initial render is a lot more expensive with useMemo, but subsequent re-renders have an even bigger performance increase. In case your application has data/processing of complexity >5000 and has a few re-renders, we can see the benefits of using useMemo.**

---

![](https://miro.medium.com/max/2400/1*UhJk3l5gIvJtmBLvUJhSMw.png)

---

> Specifically the cost for useCallback and useMemo are that you make the code more complex for your co-workers, you could make a mistake in the dependencies array, and you're potentially making performance worse by invoking the built-in hooks and preventing dependencies and memoized values from being garbage collected. Those are all fine costs to incur if you get the performance benefits necessary, but it's best to measure first.

**Kent C. Dodds**

---

## Sources

- https://kentcdodds.com/blog/usememo-and-usecallback
- https://dmitripavlutin.com/use-react-memo-wisely/
- https://dmitripavlutin.com/dont-overuse-react-usecallback/
- https://dmitripavlutin.com/react-usememo-hook/
- https://blog.bitsrc.io/5-recommended-tools-for-optimizing-performance-in-reactjs-29eb2a3ec46d
- https://medium.com/swlh/should-you-use-usememo-in-react-a-benchmarked-analysis-159faf6609b7

- https://www.youtube.com/watch?v=F8EvdTsl6hU
- https://www.youtube.com/watch?v=bm7wyCDJ7H8
