# MIS500ProjPort
Data Analysis Reactor Age vs Power Capacity

#Load library
library(dplyr)

#Load data set
mydata<- read.csv('reactors-operatingNEW.csv')

#Load data set- 2018 Power Capacity 
mydata$X.20

#Changes a factored string to numeric
mydata$X.20<-as.numeric(as.character(mydata$X.20))

#Prints out 2018 Power Capacity data into a numeric string
newdata<-as.numeric(mydata$X.20)
newdata

#Load data set- 2008 Power Capacity
mydata$X.30

#Changes a factored string to numeric
mydata$X.30<-as.numeric(as.character(mydata$X.30))

#Prints out 2008 Power Capacity data into a numeric string
initialdata<-as.numeric(mydata$X.30)
initialdata

#Omits missing and null values for 2018 and 2008 Power Capacity
mydata_18<-na.omit(newdata)
mydata_08<-na.omit(initialdata)
mydata_18
mydata_08

#Loads first 30 values for 2018 and 2008 Power Capacity
data18<-c(mydata_18[1:30])
data08<-c(mydata_08[1:30])

#Create data frame for 2018 and 2008 Power Capacity data information
my_data<- data.frame(year=rep(c("2018", "2008"), each=30), PWR=c(data18, data08))

print(my_data)

#Summary of Statistics-2018
summary(data18)

#Summary of Statistics- 2008
summary(data08)

#Compute Unpaired Two Sample T-test
res<-t.test(data18, data08, var.equal=TRUE)
rest
