# Blockchain-Intern
Assignment
const {Connection,PublicKey,clusterApiUrl,Token,TokenSwap} = require('@solana/web3.js');
const connection = new Connection(clusterApiUrl('mainnet-beta'), 'confirmed');
const tokenSwapProgramId = new PublicKey('SwaPp7sEt1HLK7kGc4Yk6KmK4Et1HLK7kG');

const tokenA = new PublicKey('So11111111111111111111111111111111111111112');
const tokenB = new PublicKey('EKpQGSJtjMFqKZ9KQanSqYXRcF8fBopzLHYxdM65zcjm');

const amount = 1;

const swapTransaction = new TokenSwap(connection,tokenSwapProgramId,tokenA,tokenB,amount).swap();

const signature = await connection.signAndSendTransaction(swapTransaction,[EuxDHFJdvWNZ9et9Xjg3PpFrozFYUg1U3bEaA1e5k7Ee]);

console.log(`Swap successful! Signature: ${signature}`);
