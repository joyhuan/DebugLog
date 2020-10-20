# Git User Remote Session 

## Bug
I used VSCode to connect to remote session to run codes in certain environment and to commit. The remote session links to an organization; I have one Git account in that organization and one Git account for my personal usage (which is this one). When I commit through that remote host, it shows that the commit was made by the organization Git account instead of my personal one. However, I do need my personal Git to show the update. (By the way the weekly breakdown is not accurate) 

## Cause
I ignored this issue for a while because 

1. it does not matter that much given I get my work done 
2. I thought it was due to either 
  a. I was connecting to the organization remote host 
  b. I used that org Git account to get org IDE license 
3. I already got tired when I'm done with coding 

## Solution
```$ git config --global user.email "joy@example.com"```

## Thought
The one-liner solution seems like no-brainer, but it does require thoughts. 

## Side
Sometimes people just need to get annoyed to a point before they start to make life easier. 
