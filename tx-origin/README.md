# Prevention
You should use msg.sender instead of tx.origin to not let this happen. There is almost never a good use case for tx.origin except in very specific cases - and in those times, be VERY careful.

Example:
```
function setOwner(address newOwner) public {
    require(msg.sender == owner, "Not owner" );
    owner = newOwner;
}
```
