# Maintain One Year Old Microservices Project

## Bug
I rarely have a chance to maintain a project. [This](https://github.com/joyhuan/MicroservicesBenchmark) was my master capstone microservice project finished one year ago. When I reran it after one year, I got tons of error message. Since the project is orchestrated by Docker, I knew immediately the error was due to some outdated package.

## Cause
I end up solve four different errors before getting the project to run again. I came across a git issue as well.

1.

2.
```
The grpc package is now deprecated and will not receive further updates other than security fixes. We recommend using @grpc/grpc-js instead.
```
3.

4.
```
package.json is not defined by "exports"
```
The Git issue 
```
$ git commit
error: invalid object 100644 13da9eeff5a9150cf2135aaed4d2e337f97b8114 for 'spec/routing/splits_routing_spec.rb'
error: Error building trees
```
## Solution 
1. "karma" has dependency on "jasmine-core" to have a version greater or equal to 3.8.0 and I just need to update the "jasmine-core" version in package.json 
2. replace the line `grpc": "^1.24.6` to `npm install @grpc/grpc-js`
3.
4.

The Git issue 
I found it in this Stack Overflow [page](https://stackoverflow.com/questions/14448326/git-commit-stopped-working-error-building-trees)
This error means that you have a file with hash 13da9eeff5a9150cf2135aaed4d2e337f97b8114, and this hash is not present in .git/objects/../, or it's empty. You just need to generate the object hash: `git hash-object -w <file_path>` 

## Thought

## Side
