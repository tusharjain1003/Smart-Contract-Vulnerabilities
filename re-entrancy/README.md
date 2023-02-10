# Prevention
There are two things you can do.

1. Either, you could recognize that this function was vulnerable to re-entrancy, and make sure you update the user's balance in the withdraw function before you actually send them the ETH, so if they try to callback into withdraw it will fail.

2. Alternatively, OpenZeppelin has a ReentrancyGuard library that provides a modifier named nonReentrant which blocks re-entrancy in functions you apply it to. It basically works like the following:

```
modifier nonReentrant() {
    require(!locked, "No re-entrancy");
    locked = true;
    _;
    locked = false;
}
```

If you were to apply this on the withdraw function, the callbacks into withdraw would fail because locked will be equal to true until the first withdraw function finishes executing, thereby also preventing re-entrancy.