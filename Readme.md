npm run test
Connection.test.js
-->beforeEach()
-->beforeEach(()=>{})

~~~~~~~~~~~~~~~~~~~~~~~
beforeEach(()=>{
    console.log("get account from ethereum")
})
describe("Chat Test",()=>{
    it("deploy a contract",()=>{})
})
~~~~~~~~~~~~~~~~~~~~~~~~~~

beforeEach(()=>{
    console.log("get account from ethereum")
})
describe("Chat Test",()=>{
    it("deploy a contract",()=>{})
})
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
npm test test\Connection.test.js
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
const ganache = require("ganache-cli")
const W3 = require("web3")
const web3 = new W3(ganache.provider())
beforeEach(() => {
    console.log("get account from ethereum")
    web3.eth.getAccounts().then((fetchAccounts)=>{
        console.log(fetchAccounts)
    })
})
describe("Chat Test", () => {
    it("deploy a contract", () => { 
        console.log("All right, I already got the accounts?")
    })
})
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
https://github.com/ChainSafe/web3.js/tree/v1.3.4

https://web3js.readthedocs.io/en/v1.3.4/web3-eth.html

connection_sync.test.js
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
const ganache = require("ganache-cli")
const W3 = require("web3")
const web3 = new W3(ganache.provider())
let fetchAccounts;
beforeEach(async () => {
    console.log("get account from ethereum")
    fetchAccounts = await web3.eth.getAccounts()
    console.log("beforeEach finished")
})
describe("Chat Test", () => {
    it("get all accounts", () => {
        console.log("is it an array?", Array.isArray(fetchAccounts))
        console.log("the type is==>", typeof fetchAccounts)
        console.log(fetchAccounts)
    })
    it("get first account", () => {
        console.log(fetchAccounts[0])
    })
})
describe("type test", () => {
    it("int is array?", () => {
        const x = 5
        console.log("is it an array?", Array.isArray(x))
    })
})

async test
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
contract("vanilla test", (accounts) => {
    it("get account", () => { })
    it("get balance", () => { })
})
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
truffle test test\Contract1.test.js
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
const Chat = artifacts.require("../contracts/Chat.sol")
contract("vanilla test", (accounts) => {
    it("get account", () => {
        console.log("first account:", accounts[0])
    })
    it("get balance", () => { 
        balance = web3.eth.getBalance(accounts[0])
        console.log("balance=",balance)
    })
});

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
const Chat = artifacts.require("../contracts/Chat.sol")
contract("vanilla test", (accounts) => {
    it("get account", () => {
        console.log("first account:", accounts[0])
    })
    it("get first balance", async () => { 
        const balance = await web3.eth.getBalance(accounts[0])
        console.log("balance=",balance)
    })
    it("get second balance", async () => { 
        const balance = await web3.eth.getBalance(accounts[1])
        console.log("second balance=",balance)
    })
});

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
integrated.terminal


{
    "git.confirmSync": false,
    "editor.fontSize": 24,
    "editor.fontFamily": "'Source Code Pro Semibold', 'Courier New', monospace",
    "terminal.integrated.shell.windows": "C:\\Windows\\System32\\cmd.exe",
}

https://www.chaijs.com/
Contract2.test.js

const Chat = artifacts.require("../contracts/Chat.sol")
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
const Chat = artifacts.require("../contracts/Chat.sol")
require("chai").use(require("chai-as-promised")).should();

let chat1
beforeEach(async () => {
    console.log("get chat deployed")
    chat1 = await Chat.deployed();
})


contract("Chat smart contract", (accounts) => {
    it("get message", () => {
        console.log("should get chat1")
        console.log(chat1)
    })
})
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
const Chat = artifacts.require("../contracts/Chat.sol")
require("chai").use(require("chai-as-promised")).should();

let chat1
beforeEach(async () => {
    console.log("get chat deployed")
    chat1 = await Chat.deployed();
})


contract("Chat smart contract", (accounts) => {
    it("get message", async () => {
        console.log("should get chat1")
        //console.log(chat1)
        let message = await chat1.getMessage();
        console.log("initial message=", message)
    })
    it("set message and get it back again", async () => {
        await chat1.setMessage("change message within chat smart contract test")
        const message1 = await chat1.getMessage();
        console.log("after change, message1=", message1)
        const message2 = await chat1.message()
        console.log("get message using public field variable:", message2)
    })
})


https://www.trufflesuite.com/boxes

https://www.trufflesuite.com/boxes/metacoin

https://github.com/truffle-box/metacoin-box


mkdir lab3_metacoin
copy .gitignore
git init
truffle unbox metacoin
yes


code .

{
    "solidity.compileUsingRemoteVersion": "v0.5.16+commit.9c3226ce"
}

README.md

# Metacoin practice
~~~~~~~~~~~~~~~~~~~~~
# Metacoin practice

### methods
```
truffle develop
```

### current accounts
```
(0) 0x7af5666106e434fec4625bee6769209ea5f87333
(1) 0x12a75550f3309a741eff3ad75dccf2da02546765
(2) 0x693dbb6533e0de7b147fcb7e1b7673650939adbc
(3) 0x27ec0062340dbbc8bcc2ec1aa80ff5a37ed9605c
(4) 0x96539429e04ab8afe9e54a15128b68101755e56e
(5) 0x3acdc1a03c6f9b590543bf72f46d40170bf56a65
(6) 0x24e41bc4233eb36efaca8fb682194bcb237e7931
(7) 0x2dbece60e3736bcb9a3ba9a177f027e420f6d1ed
(8) 0x0cb8d95b59eab696b2ae2e3d697bab8668767815
(9) 0x08e9852c0bfd8be2bee32c0fb735297fcffcf94b
```
~~~~~~~~~~~~~~~~~~~~~~~~
# Metacoin practice

### methods
```
truffle develop
> deploy
```

### current accounts
```
(0) 0x7af5666106e434fec4625bee6769209ea5f87333
(1) 0x12a75550f3309a741eff3ad75dccf2da02546765
(2) 0x693dbb6533e0de7b147fcb7e1b7673650939adbc
(3) 0x27ec0062340dbbc8bcc2ec1aa80ff5a37ed9605c
(4) 0x96539429e04ab8afe9e54a15128b68101755e56e
(5) 0x3acdc1a03c6f9b590543bf72f46d40170bf56a65
(6) 0x24e41bc4233eb36efaca8fb682194bcb237e7931
(7) 0x2dbece60e3736bcb9a3ba9a177f027e420f6d1ed
(8) 0x0cb8d95b59eab696b2ae2e3d697bab8668767815
(9) 0x08e9852c0bfd8be2bee32c0fb735297fcffcf94b
```
# get instance
```
const instance = await MetaCoin.deployed()
typeof instance
instance
const accounts = await web3.eth.getAccounts()
const balance = await instance.getBalance(accounts[0])
balance
balance.toNumber()
```
### balance.toNumber <-- this is a function

### clarify var, let, const
```
let x = 5
x=6
x
const y = 5
y=6

let p = [100]
p[0]
p[0]=101
p[0]
const q = [100]
q[0]
q[0]=101
q[0]
p = [200]
p[0]
q = [200]
```