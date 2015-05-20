### BasicsOfR
#Loading and splitting the data
#We can either drop file in the dir or create a path and read 
Airlines = read.csv(file = "C:\\Users\\admin\\Desktop\\AirlineDelay.csv")

#Data here is plit using indexes because dependent var is continous here.The sample.split function is typically used to split data with a categorical dependent variable
spl = sample(nrow(Airlines), 0.7*nrow(Airlines))
AirlinesTrain = Airlines[spl,]
AirlinesTest = Airlines[-spl,]


##Now Suppose dependent var is categorical, then we use split function
library(caTools)
set.seed(3000)
spl = sample.split(Airlines$TotalDelay, SplitRatio=0.7)
AirlinesTrain = subset(Airlines, spl==TRUE)
AirlinesTest = subset(Airlines, spl==FALSE)
