## This is a Readme.md

# Issue on Lesson 9
I had issue with running 'testFulfillRandomWordsPicksAWinnerResetsAndSendsMoney' and asked on discussion section. 
This is a fixed error version of the repo. (video is around 6h-ish of https://www.youtube.com/watch?v=sas02qSFZ74&t=21128s)

discussion: https://github.com/Cyfrin/foundry-full-course-f23/discussions/922

Raffle.sol
```solidity
(bool success, ) = winner.call{value: address(this).balance}(" ");
```
to 
```solidity
(bool success, ) = winner.call{value: address(this).balance}("");
```

Another panicking issue was while runnig fork test error with expectRevert of `testPerformUpkeepRevertsIfCheckUpkeepIsFalse()`
This was resolved by changing `DeployRaffle.s.sol`
`vm.startBroadcast();` ❌ to
`vm.startBroadcast(deployerKey);` ✅
check the process of solving by discussion section[https://github.com/Cyfrin/foundry-full-course-f23/discussions/939]
