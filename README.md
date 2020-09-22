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

# Configuring Git (On Developer's Machine)
hostname
git config --global user.name "sk76"
git config --global user.email "t2rajma33@gmail.com"
git config --global credential.helper  'cache --timeout=28800'
git config --list 


# Initialize local repository
cd /root/java_project/
ls
cd javawebapp
git init
ls
ls -a
# .git --> local repository
ls .git
ls

# Link the Local Git Repository with the Remote Github Repository
pwd
ls
ls -a
git remote add origin https://github.com/sk76/ncelllab1.git
git config --list


# Pull Codes/files from Remote Repository to the Local Repository (Note: Do it for the first time before pushing the local files to the remote repository)
pwd
ls
git pull origin master
ls


# Record the local changes/newly created files/dirs into the Staging Area
git add -A

# git add -A --> To record/update all the modifications or newly added files/dirs into the local repository


# Commit the Changes to the Local Repository
ls
git commit -m "first commit"
ls -a


# Push the Content of Local repository to the Remote Repository (i.e. Github Repository)
pwd
ls
git push origin master

# Working Directory --> (git add) Staging Area --> (git commit) Local Repository --> (git push) Remote Repository


# To Add Selected Files to the Staging Area

git status --> Displays status of currently added/commited files
vi file1
vi file2
git status
rm README.md 
ls
git status
git push origin master
git status
git add file1
git status
git commit -m "file1 added"
git status
git push origin master
git status
git add -A
git status
git commit -m "file2 added and README deleted"
git status
git push origin master


# Undo Chagnes
git status
ls
vi file1
git status

# Case-I: File has been modified but not sataged yet
cat file1
git status
vi file1
cat file1
git checkout file1
cat file1
git status

# Case-II: Changes added into the staging area but not committed yet
vi file1
cat file1
git status
git add file1
git status
cat file1
git checkout file1 --> will not work
cat file1 --> undo not performed
git reset HEAD file1
git checkout file1
cat file1 --> undo takes place
git status

Case-III: Changes have been staged and committed
vi file1
git status
git add file1
git status
git commit -m "file1 modified"
git status
cat file1
# git log --> Displays commit history
git log
revert -n 5354a6ecc39d5ef3e1557f493f2da1a3253f163c
cat file1
git status
git add file1
git commit -m "new commit for file1"
git status
cat file1
