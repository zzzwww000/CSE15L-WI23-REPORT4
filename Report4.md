# **CSE15L REPORT 4**

Created by: Zichen Wang

## **Notes**

1. I have created a cheatsheet utilizing the contents from labs:

```
MAC：
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests

WIN:
javac -cp ".;lib/hamcrest-core-1.3.jar;lib/junit-4.13.2.jar" *.java
java -cp ".;lib/junit-4.13.2.jar;lib/hamcrest-core-1.3.jar" org.junit.runner.JUnitCore ListExamplesTests
```
2. According to the requirements of the Lab Report, the report begins from "Step 4"; The previous steps includes:

```
1 Setup Delete any existing forks of the repository you have on your account
2 Setup Fork the repository
3 The real deal Start the timer!
```


## **Step 4**

Log into the ieng account provided in UCSD account.
(This step may be skipped according to our generation of ssh key)

Keys typed:
```
ssh <ucsd ieng6 account> <enter>
<password> <enter>
```

See screenshots:

![LOGIN](https://user-images.githubusercontent.com/120359926/221451750-940a2198-ee7d-4b9c-b548-ab397eea7ab4.png)
![LOGIN2](https://user-images.githubusercontent.com/120359926/221451757-b9f16ea0-449b-4080-9a3b-d422a4204f35.png)



## **Step 5**
Clone the fork from my own github account: using command `Git Clone`

> This step can be facilitated by using `Ctrl + C` and `Ctrl + V` for the github link

Keys typed:
```
<ctrl + c>, git clone, <ctrl + v> <enter>
ls <enter>
```

```
[cs15lwi23alb@ieng6-202]:~:344$ git clone git@github.com:zzzwww000/CSE15L-LAB7.git
Cloning into 'CSE15L-LAB7'...
Warning: Permanently added the RSA host key for IP address '140.82.113.4' to the list of known hosts.
remote: Enumerating objects: 42, done.
remote: Counting objects: 100% (6/6), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 42 (delta 0), reused 4 (delta 0), pack-reused 36
Receiving objects: 100% (42/42), 374.69 KiB | 1.39 MiB/s, done.
Resolving deltas: 100% (12/12), done.
[cs15lwi23alb@ieng6-202]:~:345$ ls
CSE15L-LAB7  perl5
```


## **Step 6**
Running the tests from our remote server: using mac commandline.

> This step can be facilitated: copying form the cheatsheet, and change the directory first.

Keys typed:
```
cd CSE15L-LAB7

<ctrl + c>, <ctrl + v> <enter>
(contents pasted: javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java)

<ctrl + c>, <ctrl + v> ListExamplesTests <enter>
(contents pasted: java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore)
```

See screenshot:

![Failed](https://user-images.githubusercontent.com/120359926/221452980-4f53b39b-d678-404e-9001-ea1eb35cc9f3.png)


## **Step 7**
To edit the code, find the buggy place first:

![bug1](https://user-images.githubusercontent.com/120359926/221453117-fc32857c-1d03-4107-bf55-bd1cdcf04ed0.png)

We can see, index2 is never updated, but a typo make index1 continue to update, which makes it run out of the boundary. So we change index1 to index2.

![bug2](https://user-images.githubusercontent.com/120359926/221453185-bf6ee8d4-c0ba-4ccc-883c-e3d751087a1e.png)

Now, send this local change to remote server by `scp` command
Use `pwd` before exiting the account to access the directory to send

And use `scp` to update our files

> I opened a different terminal to do this `scp` command in order to save some time.

Keys Typed:
```
pwd
exit
scp ListExamples.java <Ctrl + C><Ctrl + V>: <Ctrl + C><Ctrl + V> <enter>
(contents pasted1: <account of ieng6>)
(contents pasted2: /home/linux/ieng6/cs15lwi23/cs15lwi23alb/CSE15L-LAB7)
<password> (<Ctrl + C><Ctrl + V>) <enter>

<up> <enter>
<password>
```

See screenshots:

![7-1](https://user-images.githubusercontent.com/120359926/221455210-d8cee246-b400-40cf-8fa5-96cdab929c5c.png)
![7-2](https://user-images.githubusercontent.com/120359926/221455243-f952ac68-daa1-44bb-937c-fd2eee9ad64d.png)
![7-3](https://user-images.githubusercontent.com/120359926/221455333-11ace70b-ccf7-4649-91a8-b93cfbfe896a.png)

## **Step 8**
Running the commands to show how they succeed

Keys typed:
```
cd <Ctrl + C><Ctrl + V> <enter>
(contents pasted: CSE15L-LAB7)

<up> <up> <up> <up> <up> <enter>

<up> <up> <up> <up> <up> <enter>

```

See screenshot:
![8](https://user-images.githubusercontent.com/120359926/221455770-5d409daf-8db9-4d59-9646-a7644e2ee209.png)

## **Step 9**
Get those remote changes pushed to github page of my original contents

> Following commands will be useful: `git add`, `git commit -m`, `git push`

Keys typed:
```
git add .(current directory) <enter>
git commit -m "final version 2/26 17:34" <enter>
git push <enter>
```
See Screenshot:

![9](https://user-images.githubusercontent.com/120359926/221464950-2ee10594-2eb3-4bb4-bb57-ddea29ef94d8.png)
![10](https://user-images.githubusercontent.com/120359926/221695031-c7addcfa-4b59-43f7-9bcf-5a9ee1a101d0.png)

