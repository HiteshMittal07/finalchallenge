Hello Guys,
Myself Hitesh Mittal maybe you know me by the name thor11759(discord name)

So lets just start by understanding the Code of our final challenge
## DESCRIPTION:
  This contract is about creating a new token(not really) , minting and burning the amount from different address of wallets
## EXPLAINATION:
  In this code first of all we created two string variable(for storing token name and abrev) and one uint variable(for storing value to total supply)
  ```javascript
  string public token_name= "Mittal";
  string public token_abrev="Mit";
  uint public totalsupply = 0;
  ```
  Upcoming next you will find we have used mapping to map the address of wallets with amount they store:
  ```javascript
  mapping(address =>uint)public balances;
  ```
  Next we have a mint function in which we passed two arguments:
  One is address to which amount is to be assigned, and second is the amount and then we are adding the amount to both balances and totalsuppply:
  ```javascript
  function mint (address _address, uint _value) public{
        totalsupply +=_value;
        balances[_address] +=_value;
   }
   ```
  Next we have a burn function which functionality is to reduce the token amount on usage:
  In this we have provided a conditional statement so that before reducing it should check rather we have that much number of tokens or not.
  ```javascript
  function burn (address _address,uint _value) public{
        if(balances[_address] >= _value)
        {
            totalsupply -=_value;
            balances[_address]-=_value;
        }
    }
  ```
