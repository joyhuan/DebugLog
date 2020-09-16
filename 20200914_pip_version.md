# Jupyter Notebook cannot find basic modules 

## Bug
I had this problems several times when I run jupyter notebook. Once in July once in Sep. I got this in Jupyter Notebook 

```ModuleNotFoundError: No module named 'numpy'```

even though they're obviously there. This is especilly frustrating when I try to import them in local python bash and succeed. 

I know there is this annoying python2 vs python3 thing two years ago when I took ML and CV. But python2 is deprecating and this time it is not the culprit.

Following many threads of related question dated back to 2016 I fixed it again this time. 

## Cause
There was a somewhat major change between July and Sep - I deleted the directory for python 3.7 and installed python 3.8.5 as the latest version. However, I did not fully cleaned my path env variable to point elsewhere nor did I update the related alias.

## Solution
For the July fix, I did 

```python3 -m pip install numpy```

On the other hand, 

```pip3 install numpy``` does not work 

For the Sep fix, python3 does not help, I did 

```pip install jupyter```

It makes sense to reinstall jupyter - the linking needs to update for the 3.7 -> 3.8 migration. 

## Thought
It is useful to know what version and where you installed the packages 

```python --version``` 

```which python```  

are the helpful/useful commands. 

Dependencies are sometimes hidden. Like this time I forgot to update env variables and alias. They cause subtle problems. 

## Side
I felt quite peaceful when figuring out the solution and time flies. This is the first time I consciously realized it. 
