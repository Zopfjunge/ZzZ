function generatePrevHash(prevHash, length=100){
  for (let i = 0; i < length; i++) {
    let hash = String(CryptoJS.SHA256(String(prevHash))); //We're using the CryptoJS javascript library https://www.npmjs.com/package/crypto-js
    let bust = gameResult(hash); //the gameResult calculation function above
    console.log(`HASH: ${hash}, crash point: ${bust}, index: ${i}`); //printing the result to the console
    prevHash = hash;
  }
}
