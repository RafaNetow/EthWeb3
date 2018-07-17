# EthWeb3
Installing & Running the Ethereum TestRPC
The Ethereum TestRPC is a Node.js Ethereum client for the testing and developing smart contracts. Because it's based on Node.js, we need Node.js installed along with NPM (Node Package Manager) to install it.

Open up your command line or console and run the following 2 commands:

> node -v
> npm -v
If either of these commands go unrecognized, visit Nodejs.org and download the appropriate installer. Run it through all of the default options.

Once finished, close and reload your console and re-run the commands above. They should now provide you with version numbers.

Next, let's use NPM to install the Ethereumjs-testrpc:

> npm install -g ethereumjs-testrpc
Once finished, run the following command to start it:

> testrpc
This provides you with 10 different accounts and private keys, along with a local server at localhost:8545.


Changing the Environment in Remix
Switch over to the Remix IDE, click on the Run tab, and then change the Environment dropdown from Javascript VM to Web3 Provider.

Hit "OK" and then specify the testrpc localhost address (by default, it's http://localhost:8545)

This means that instead of deploying and testing in the Javascript VM, we're now using the TestRPC client on your computer.

If you haven't been following along since the previous lesson, paste in this contract in a new solidity file called "Coursetro.sol":

pragma solidity ^0.4.18;

contract Coursetro {
    
   string fName;
   uint age;
   
   function setInstructor(string _fName, uint _age) public {
       fName = _fName;
       age = _age;
   }
   
   function getInstructor() public constant returns (string, uint) {
       return (fName, age);
   }
    
}