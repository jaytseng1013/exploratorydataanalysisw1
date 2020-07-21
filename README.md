# exploratorydataanalysisw1
getwd()
setwd("C:/Users/tseng/Desktop")
data <- read.table(file = "household_power_consumption.txt", sep = ";", header = TRUE, stringsAsFactors = FALSE)
twoday<-subset(data, Date == "1/2/2007" | Date == "2/2/2007")
na.strings = "?"
as.numeric(as.character(twoday$Global_active_power))
GAP<-as.numeric(twoday$Global_active_power)
hist(GAP,col="red",main="Global Active Power",xlab="Global Active power")
