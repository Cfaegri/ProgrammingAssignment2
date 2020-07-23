

## Writing my functions: 

## 1.  `makeCacheMatrix`: This function creates a special "matrix" object
    that can cache its inverse.


makeCacheMatrix <- function(x=matrix()){
  inv <- NULL
  set <- function(y){
    x <<- y
    inv <<- NULL
  }
  get <- function() {x}
  setInverse <- function(inverse) {inv <<- inverse}
  getInverse <- function() {inv}
  list(set=set, get=get, setInverse=setInverse, getInverse = getInverse)
}





## 2.  `cacheSolve`: This function computes the inverse of the special
    "matrix" returned by `makeCacheMatrix` above. If the inverse has
    already been calculated (and the matrix has not changed), then
    `cacheSolve` should retrieve the inverse from the cache.

cacheSolve <- function(x,...){
  inv <- x$getInverse()
  if(!is.null(inv)){
    message ("getting cached data")
    return(inv)
  }
  mat <- x$get()
  inv <-solve(mat,...)
  x$setInverse(inv)
  inv
}





## In order to complete this assignment, you must do the following:


4.  Commit your completed R file into YOUR git repository and push your
    git branch to the GitHub repository under your account.
5.  Submit to Coursera the URL to your GitHub repository that contains
    the completed R code for the assignment.

### Grading

This assignment will be graded via peer assessment.



