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

Malicious Contract's Address: 0x5FbDB2315678afecb367f032d93F642f64180aa3

Good Contract's Address: 0xe7f1725E7734CE288F8367e1Bb143E90bb3F0512