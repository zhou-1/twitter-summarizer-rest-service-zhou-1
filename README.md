# Goal    
Make my ["Convert Tweet contents to a video" program](https://github.com/zhou-1/video-zhou-1) a REST service running on AWS       
https://zhou-1.github.io/twitter-summarizer-rest-service-zhou-1/  

## Details   
Step 1: Use Flask as your WEB service platform     
Reference 1:  https://palletsprojects.com/p/flask/ (Github:  https://github.com/pallets/flask )   
Reference 2:  Flask-RESTFUL  (Github:  https://github.com/flask-restful/flask-restful )     
Use Python and Flask to achieve the RESTful services.    

Step 2:  Integrate your module to become a RESTFUL system   
Deploy your system to free AWS services:  https://aws.amazon.com/free/?all-free-tier.sort-by=item.additionalFields.SortRank&all-free-tier.sort-order=asc    
Develop simple WEB applications to test your system.      

## Caution  
Document your REST APIs on your Github    
Keep your server off until we request it for grading.  We dont want you to waste money.     

# Set up    
## Flask    
Command for downloading Flask using pip     
```
pip install -U Flask
```
## Flask-RESTful     
Install Flask-RESTful with pip    
```
pip install flask-restful
```

### Examples    
#### Flask &Flask-RESTful     
Examples can be [viewed here](https://github.com/BUEC500C1/twitter-summarizer-rest-service-zhou-1/tree/master/FlaskProj)    

## This project   
clone this repo     
```
git clone https://github.com/BUEC500C1/twitter-summarizer-rest-service-zhou-1.git
```

Install all requirements for this program   
```
pip3 install -r requirements.txt
```

<b> Important! </b> Please go to keys file, to add in your own Tweepy API keys in below format:
```
[auth]
consumer_key = ****
consumer_secret = ****
access_token = ****
access_secret = ****
```

### Run this program    
On your shell/terminal, run this program by typing below command:   
```
python flaskWeb.py
```
Then you can go to link: http://127.0.0.1:2000/ to see the main page. (>1000 port: no need permission from root)       
The index page will be looked like below:    
![index](imgs/Main.PNG)     

Once you type in the Twitter ID you would like to search for, click the submit button; the program will take you to download page directly. Download page looks like below:
![download](imgs/download.PNG)     

### Run AWS and App    
Connect to Your Linux Instance using an SSH Client:   
```
ssh -i /path/my-key-pair.pem ec2-user@ec2-198-51-100-1.compute-1.amazonaws.com   
```
Then run the program:   
```
sudo python3 flaskWeb.py
```

You can go to one of the below webpages:             
ec2-54-193-45-110.us-west-1.compute.amazonaws.com:2000   
Or another link    
http://54.193.45.110:2000/

Ubuntu instance looks like below:   
![ubuntu](imgs/ubuntu.PNG)   


## Tips   
### “Unable to locate package python-pip” When try to install     
You have to enable universe category which contains python-pip package.     
Open /etc/apt/sources.list using an editor, for example nano:     
```
sudo nano /etc/apt/sources.list
```
then add universe at the end of each line, like this:    
```
deb http://archive.ubuntu.com/ubuntu bionic main universe
deb http://archive.ubuntu.com/ubuntu bionic-security main universe 
deb http://archive.ubuntu.com/ubuntu bionic-updates main universe
```
Press Ctrl+O to save the file.    
then run:   
```
sudo apt update
```
and finally:    
```
sudo apt install python-pip
```


## Test
For pytest, I tested results for whether required videos exist or not by comparing the names; All tests passed.    

For testing for whether keys file exist or not, whether keys file is empty or not, whether keys file has main and sub title or not; if answer for any of them is no, we need to call get_oldJson function. This function is in tweepyInfo.py file.    

Caution: In order to use my get_oldJson function successfully, you need to have json file for the desired twitter account first. I had already put in default 10 twitter user's tweets in jsonFolder; therefore, if keys file fail, we can get information from previous json file.   
Moreover, every time out program successfully with right keys file, json files for those twitter account will get updated, too.   













