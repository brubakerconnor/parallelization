library(doParallel)
registerDoParallel(8)

n <- 25000
x <- iris[which(iris[,5] != "setosa"), c(1,5)]
stime <- system.time({
  r <- for(i in 1:n) {
    ind <- sample(100, 100, replace = TRUE)
    result1 <- glm(x[ind,2] ~ x[ind,1], family = binomial(logit))
    coefficients(result1)
  }
})
print(stime) # 13.720

ptime <- system.time({
  r <- foreach(i = 1:n) %dopar% {
    ind <- sample(100, 100, replace = TRUE)
    result1 <- glm(x[ind,2] ~ x[ind,1], family = binomial(logit))
    coefficients(result1)
  }
})
print(ptime) # 3.140
