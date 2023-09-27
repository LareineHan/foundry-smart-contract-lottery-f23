# This is a Readme.md

I had an issue with running 'testFulfillRandomWordsPicksAWinnerResetsAndSendsMoney' and asked on discussion section. 
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
