# Step One:
Objective: create a maven package in the local repository. 

Software: Eclipse 

### 1.
> Eclipse File – new – project 

![Image of Yaktocat](![Image of Yaktocat](https://image.baidu.com/search/detail?ct=503316480&z=0&ipn=d&word=图片&step_word=&hs=0&pn=4&spn=0&di=178640&pi=0&rn=1&tn=baiduimagedetail&is=0%2C0&istype=0&ie=utf-8&oe=utf-8&in=&cl=2&lm=-1&st=undefined&cs=151472226%2C3497652000&os=965075743%2C225091002&simid=3313919698%2C393785477&adpicid=0&lpn=0&ln=1490&fr=&fmq=1602050822858_R&fm=&ic=undefined&s=undefined&hd=undefined&latest=undefined&copyright=undefined&se=&sme=&tab=0&width=undefined&height=undefined&face=undefined&ist=&jit=&cg=&bdtype=0&oriquery=&objurl=http%3A%2F%2Fa3.att.hudong.com%2F57%2F28%2F01300000921826141405283668131.jpg&fromurl=ippr_z2C%24qAzdH3FAzdH3Fp7rtwg_z%26e3Bkwthj_z%26e3Bv54AzdH3Ftrw1AzdH3Fwn_c0_db_a8naaaaald8bdm8989acdbnmmb8n8_3r2_z%26e3Bip4s&gsm=6&rpstart=0&rpnum=0&islist=&querylist=&force=undefined)
 

> Choose Maven Project (left)  ---- Use default workspace location (right)

  

> Choose maven-archetype-quickstart

 
> Then put in some basic information, group id and artifact id. 
 
### 2.	

Under project in the left control panel, find App.java under src/main/java and then under Java2. Project. App.java is where you can put in the code you want (here shown is a simple default “helloworld” code. 
 


### 3.	

Click on the project --- Run as --- 4 Maven Build
 

Goals: package
 
Then, if this is successfully run, you should see the following message: 
 

### 4.	

(this step is not necessary for all eclipse users)

a)	Problem: 
Failed to run successfully initially, and had the following message:
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-compiler-plugin:3.1:compile (default-compile) on project groupproject: Compilation failure: Compilation failure: 
[ERROR] Source option 5 is no longer supported. Use 7 or later.
[ERROR] Target option 5 is no longer supported. Use 7 or later.
[ERROR] -> [Help 1]
[ERROR] 
[ERROR] To see the full stack trace of the errors, re-run Maven with the -e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR] 
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/MojoFailureException

b)	Solution: 
In pom.xml, replace
 <properties>
    <project.build.sourceEncoding>UTF-8 </project.build.sourceEncoding>
  </properties>

With 
<properties>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
       <java.version>1.8</java.version>
       <maven.compiler.source>1.8</maven.compiler.source>
       <maven.compiler.target>1.8</maven.compiler.target>
</properties>
  
Then, you should see the build success message in step 3!

### 5.	

The last step is to turn it into a local repository. 

Click on the project—run as (again) – 4 Maven build (same as before)
 

(different) Goals: install 
 

Then, you should see the build success message again!

### 6.	

Lastly, run the following commands in the terminal
 

The “Project-0.0.1-SNAPSHOT.jar” file is the file you want to share with others!

