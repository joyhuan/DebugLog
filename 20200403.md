# Resume App Update Stuck in "waiting" Mode in Mac App Store 

## Bug
When I updated Pages and Numbers from Mac App Store, they are stuck in "waiting" mode with a 
transparent progress bar with 0 progress. Clicking on these two apps does no help. 

## Cause 

## Solution 
Following [this post](https://apple.stackexchange.com/questions/54441/how-to-remove-an-app-stuck-in-waiting-mode-from-the-mac-app-store)
```
In the Activity Monitor, for example, kill the storeagent process. Then restart App Store 
and click resume. That's it. 
```
There are CPU, Memory, Energy, Disk, Network in Activity Monitor. Obviously CPU is the most relavent 
one. I typed *storeagent* and two processes show up -- appstoreagent and ContextStoreAgent. After
killing the appstoreagent process, the issue is still not resolved. So I continue to try to kill 
ContextStoreAgent. However, it cannot be killed. So I restarted the laptop, and now both Pages and 
Numbers gets updated properly. 

## Thought
Even before I touch any CS concept, I know that when something goes wrong, restarting the system 
might help -- this is known by many people agnostic of any CS concepts from my experience. But why?
Where is the idea from? 

When something stops working, one of the valid guesses is that it is stuck in some infinite loop due
to some malfunctioning detours. To get it out of the loop, the simplest way is to let it run another 
time. There is a high probability that it won't stumble on the the unexpected route. 

When we are agnostic to what the error is and where it lies in and it does not worth the time digging
in, it is not a bad idea to Format and let everything reset to default by rebooting. That's the 
tuition independent of the subject CS. 

## Side
This is not strictly technical, but it is still a bug and uses some common sense of computer. 

