# Prevention
Make the address of the external contract public and also get your external contract verified so that all users can view the code

Create a new contract, instead of typecasting an address into a contract inside the constructor. So instead of doing Helper(_helper) where you are typecasting _helper address into a contract which may or may not be the Helper contract, create an explicit new helper contract instance using new Helper().

Example
```
contract Good {
    Helper public helper;
    constructor() {
        helper = new Helper();
}
```

