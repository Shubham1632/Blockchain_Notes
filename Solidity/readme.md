Solidity-

- What is Solidity-
	- a programming language that is used to write smart contract on the ethereum blockchain
	- build with with reference from c++, python, and javascript ( has features of these languages)
	- statically typed language
- modifiers -
	- are conditionals to run the functions
	- we can use as many as modifiers we want
	- read about them properly
- Data types-
	- string , uint, bool, address(walletaddress), array ( string[] namelist), struct   ----> (like c++)
	- read about address, bytes, modifiers, uint (why not int), enums
	- units -
		- coins --> ether, wei, finney, sazbo
		- time --> seconds, minutes, hours, days, weeks
			- years has been debracated because of confiction between 365 and 364 days
		- ( you cant make variables with them but can use in smart contract )
	- Enum-
		- like human defined variables having restricted custom values that can be set
		- to restrict the variable to have only predefined values
		- internally represeted as uint
		- 
	- Mappings -
		- just like hashmaps
		- stored in key value pair
		- Syntax-
			- normal ---> mapping( key => value ) name;
				- you can delete it by --> delete name[ param ];
			- nested ---> mapping( key => mapping( nestedkey => value ) ) name;
				- can access through ---> name[ key ] [ nestedkey ]
- Events -
	- are used for logging in the blockchain
	- these logs can be later parsed to provide some info to the front-end 
	- used as a cheap option to store data
- Special variables-
	- Block-
		- Solidity has a block object with which we can interact 
		- ex-
			1. block.number ---> get the number of block
			2. block.difficulty ----> read about it*
			3. block.coinbase ---> can get address of miner
	- Msg-
		- msg.sender ---> get senders address
		- msg.value ---> get the value added in transcaction
		- msg.data ---> read about it*
- Functions-
	- function <function_name> ( <params> ) <modifires> returns ( <params> ) { }
	- we intialize variables in the returns iteslef ---> it return that specific variable automatically
	- view and pure
		- view - 
			- will not change any state variable but can read the state variables
		- pure-
			- cannot change or read the state variable 
			- completely isolated from contract data
	- Payable Functions->
		- a function specifier through which we can transfer the ether  to our contract.
- Inheritance-
	- solidity provides inheritance just like other languages
	- to inherit a contract you have to write "is" keyword 
		- contract A { }
		- contract B is A { }    ---->  B is inherting A
	- to get inherited, a parent function must specify its functions as "virtual"
		- int contract A ----> function fun() public virtual return (uint) { }
	- to inherit a parent contract you must write "override"
		- int contract B ---> function fun() public override returns (uint) { }
- Transferring the eth-
	- currently recommended method is to use call function
		- (bool success, bytes memory data) = _to.call{ value: msg.value } ("");
		- here _to is the address of the person you want to send the data to ( first you have to declare _to as a payable address)
			- address payable _to = payable(<address>)
		- call function returns the boolean value ( is the transaction is successful or not) and a bytecode that describes the data'
	- alternate method-
		- transfer -> _to.transfer(<amount> ether);
	- getting the balance of the current address->
		- address(this).balance;
		- or any other _address.balance
- Importing -
	- workes like importing in node.js or other languages
	- internal imports-
		- import "./fun.sol"
	- external imports-
		- import "https://github.com/Shubham1632/solidity/fun.sol"
- Libraries-
	- libraries cant contain any state variable 
	- also cant do the transactions or trancefer eth
	- mostly use for like to add helper function
		- safeMath is most commonly used library
		  
                  
















