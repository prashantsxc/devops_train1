# devops_train1

# 1. Download Maven

mkdir /opt/maven
cd /opt/maven
pwd
wget https://downloads.apache.org/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.tar.gz
ls
tar -zxvf apache-maven-3.6.3-bin.tar.gz 
ls
cd apache-maven-3.6.3/
ls
cd bin
ls
pwd

# 2 Set Path of Maven Binary

echo $PATH
vi /root/.bashrc 
(bottom)
M2_HOME=/opt/maven/apache-maven-3.6.3
M2=$M2_HOME/bin
PATH=$PATH:$M2_HOME:$M2

echo $PATH
source /root/.bashrc 
echo $PATH
which mvn


***creating java application using maven template

Day-10

Agenda:
1.	Creating a Java-based Web Application Using Maven for HelloWorld
2.	Comping the Java-based Application
3.	Packaging the Java-based Application into WAR file (this WAR file is deployed on the application server like tomcat)
# Creating a Web-Based Java Application Using Maven Template (ON DEVELOPER's MACHINE)

  mkdir /root/java_project
  cd /root/java_project
  ls
  mvn archetype:generate -DgroupId=com.pis -DartifactId=javawebapp  -DarchetypeArtifactId=maven-archetype-webapp  -DinteractiveMode=false
  ls
  cd javawebapp/
  ls
  yum -y install tree
  ls
  tree .
  vi src/main/webapp/index.jsp 
  ls
  cat pom.xml

 # Comping the Java Webapplication
  mvn compile
  ls
  ls target/
  ls target/classes/
  
 # Topic: Git
# Installing Git (On Developer's Machine)
hostname
yum -y install git
# git --version --> To see Git's version
git --version


# Creating an account on Github (https://github.com)
#SignUp
# Username:
# EmailId:
# Password:
# Verify Your Account (email login, click on verify link)
# Solve Puzzle
# Select Plan: free
# Verify your email
# signout
# signin

# Creating a Repository in Github

Repository --> New --> Name: reponame  --> Public --> Initialize README file --> Create 

# Conf
sanjiv karn10:45 AM
# Configuring Git (On Developer's Machine)
hostname
git config --global user.name "sk76"
git config --global user.email "t2rajma33@gmail.com"
git config --global credential.helper  'cache --timeout=28800'
git config --list
