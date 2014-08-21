## This is a markdown file
if (!file.exists("data")){dir.create("data")}
fileUrl<-"https://d396qusza40orc.cloudfront.net/getdata%2Fdata%2Fss06hid.csv"
download.file(fileUrl,destfile="./R_codes/data/ACS_survey.csv")
ACSdata<-read.csv("./data/ACS_survey.csv",head=TRUE,sep=",")
length(ACSdata$VAL[!is.na(ACSdata$VAL) & ACSdata$VAL==24])

 fileUrl1 <- "https://d396qusza40orc.cloudfront.net/getdata%2Fdata%2FDATA.gov_NGAP.xlsx"
download.file(fileUrl1, destfile="./R_codes/data/gov_NGAP.xlsx")

dateDownloaded <- date()
rowIndex <- 18:23
colIndx <- 7:15
dat <- read.csv("./R_codes/data/gov_NGAP.xlsx",sheetIndex=1,colIndex=colIndx,startRow=18, endRow=23, header=TRUE)
head(dat)
sum(dat$Zip*dat$Ext,na.rm=T)

fileUrl2 <- "http://d396qusza40orc.cloudfront.net/getdata/data/restaurants.xml"
doc <- xmlTreeParse(file=fileUrl2,useInternal=TRUE)
rootNode <- xmlRoot(doc)
xmlName(rootNode)
names(rootNode)
rootNode[[1]][[1]]
zipcode <- xpathSApply(rootNode,"//zipcode",xmlValue)
length(zipcode[zipcode==21231])