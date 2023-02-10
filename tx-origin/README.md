# Prevention
You should use msg.sender instead of tx.origin to not let this happen. There is almost never a good use case for tx.origin except in very specific cases - and in those times, be VERY careful.

Example:
```
function setOwner(address newOwner) public {
    require(msg.sender == owner, "Not owner" );
    owner = newOwner;
}
```
Good Contract's Address: 0x8464135c8F25Da09e49BC8782676a84730C318bC

Attack Contract's Address: 0x5FbDB2315678afecb367f032d93F642f64180aa3