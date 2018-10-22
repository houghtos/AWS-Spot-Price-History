# AWS-Spot-Price-History
Stand alone module to give historical pricing for spot EC2 instances.

## Requirements: 
1. AWS CLI to be installed and usable from your machine's command line.  
2. AWS Key/secret key and region configured from your CLI.

## Price History Object takes two inputs: 
1. EC2 machine type (e.g. m1.xlarge) 
2. Number of months prior from today you wish to see spot prices for (e.g. 3).

*Fully Customize Query:*

AMI type and other information (e.g. region) can be changed by editing [the os.system command](https://docs.aws.amazon.com/cli/latest/reference/ec2/describe-spot-price-history.html) passed to the AWS CLI on line 31 (function "describeSpotPrice()")

## Example usage: 

  	#Declare object with 2 inputs: AMI type and number of previous months to review.
	listPriceObject = comparePrice("t3.2xlarge", 3)
	
	#Calculate difference from current date to input (e.g. 3) months prior.
	listPriceObject.monthDelta()        
	
	#Submit AWS CLI shell command for describing spot instances prices.
	listPriceObject.describeSpotPrice()
