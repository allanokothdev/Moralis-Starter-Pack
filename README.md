# Moralis-Starter-Pack
Login in with Metamask 


//CONNECT TO Moralis Server
const serverUrl = "PASTE SERVER URL FROM Moralis Website";
const appId = "PASTE SERVER APP ID FROM Moralis Website";
Moralis.start({ serverUrl, appId });


//LOGOUT
logout = async () => {
    await Moralis.User.logOut();
    window.location.href = "index.html";
}


//FETCH TRANSACTIONS
 const options = { chain: "rinkeby", address: "0x5Bcf6770345C94b2822B8b4eE8a4b1e3Fd69374d" };
    const transactions = await Moralis.Web3API.account.getTransactions(options);
    console.log(transactions);
    
    
//FETCH ACCOUNT BALANCE /NETWORK
 const ethBalance = await Moralis.Web3API.account.getNativeBalance();
 const ropstenBalance = await Moralis.Web3API.account.getNativeBalance({ chain: "ropsten" });
 const rinkebyBalance = await Moralis.Web3API.account.getNativeBalance({ chain: "rinkeby" });
