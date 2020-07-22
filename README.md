# exploratorydataanalysisw1

#Plot1_start
getwd()
setwd("C:/Users/tseng/Desktop")
data <- read.table(file = "household_power_consumption.txt", sep = ";", header = TRUE, stringsAsFactors = FALSE)
twoday<-subset(data, Date == "1/2/2007" | Date == "2/2/2007")
na.strings = "?"
as.numeric(as.character(twoday$Global_active_power))
GAP<-as.numeric(twoday$Global_active_power)
hist(GAP,col="red",main="Global Active Power",xlab="Global Active power (kilowatts)")
#Plot1_end

#Plot2_start
setwd("C:/Users/tseng/Desktop")
data_full <- read.csv("household_power_consumption.txt", header=T, sep=';', na.strings="?", nrows=2075259, check.names=F, stringsAsFactors=F, comment.char="", quote='\"')
data1 <- subset(data_full, Date %in% c("1/2/2007","2/2/2007"))
data1$Date <- as.Date(data1$Date, format="%d/%m/%Y")
datetime <- paste(as.Date(data1$Date), data1$Time)
data1$Datetime <- as.POSIXct(datetime)
with(data1, {  plot(Global_active_power~Datetime, type="l",       ylab="Global Active Power (kilowatts)", xlab="")})
#Plot2_end

