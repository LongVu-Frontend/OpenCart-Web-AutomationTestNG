# OpenCart TestNG Framework - Eclipse Setup Guide

## Setup Instructions

### 1. Prerequisites
- Java JDK 17 installed
- Eclipse IDE installed
- Maven installed
- Chrome/Edge Browser installed

### 2. Import Project in Eclipse
	1. Open Eclipse IDE
	2. Go to File -> Import
	3. Select Maven -> Existing Maven Projects
	4. Browse to project folder location
	5. Click Finish

### 3. Project Structure
	OpenCart_TestNG_Framework/
	├── src/
	│ ├── main/
	│ │ └── java/
	│ └── test/
	│ └── java/
	│ ├── testCases/
	│ │ ├── TC_Register_001.java
	│ │ ├── TC_Login_002.java
	│ │ ├── TC_SearchandAddToCart_003.java
	│ │ ├── TC_CheckOut_004.java
	│ │ └── TC_PricesDDT_005.java
	│ └── utilities/
	│ └── ExtentReportsManager.java
	├── test-output/
	├── logs/
	├── screenshots/
	├── testng.xml
	└── pom.xml

### 4. Maven Dependencies
	The project uses following dependencies (defined in pom.xml):
	- Selenium WebDriver 4.26.0
	- TestNG 7.10.2
	- Apache POI 5.3.0 
	- ExtentReports 5.1.1
	- Log4j 2.23.1
	- Commons IO 2.16.1
	- Commons Lang3 3.15.0
	- SLF4J Simple 1.7.36

### 5. Configure Build Path
	1. Right click on project
	2. Properties -> Java Build Path
	3. Add Library -> JRE System Library -> JavaSE-17
	4. Add Library -> TestNG
	5. Apply and Close

### 6. TestNG Configuration
	testng.xml contains:
	- Test suite configuration
	- Browser parameter
	- Test groups
	- Test classes to execute

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE suite SYSTEM "http://testng.org/testng-1.0.dtd">
<suite name="All Test Suite">
    <listeners>
        <listener class-name="utilities.ExtentReportsManager" />
    </listeners>
    <test name="OpenCart Tests">
        <parameter name="browser" value="chrome"></parameter>
        <classes>
            <class name="testCases.TC_Register_001"/>
            <class name="testCases.TC_Login_002"/>
            <class name="testCases.TC_SearchandAddToCart_003"/>
            <class name="testCases.TC_CheckOut_004"/>
            <class name="testCases.TC_PricesDDT_005"/>
        </classes>
    </test>
</suite>
```

### 7. Running Tests
#### Method 1: Using TestNG
	1. Right click on testng.xml
	2. Run As -> TestNG Suite
#### Method 2: Using Maven
	1. Right click on project
	2. Run As -> Maven test
#### Method 3: Individual Test Cases
	1. Right click on test class
	2. Run As -> TestNG Test

### 8. View Results
	* Test results available in test-output folder
	* Extent reports generated in test-output folder
	* Screenshots captured in screenshots folder
	* Logs generated in logs folder

### 9. Eclipse-specific Files
  * .classpath: Contains classpath entries
  * .project: Eclipse project configuration
  * .settings/: Eclipse settings folder

### 10. Git Configuration
	.gitignore includes:
		target/
		.idea/
		*.iws
		*.iml
		*.ipr
		.settings/
		.classpath
		.project
		.vscode/
		.DS_Store

## Troubleshooting
1. Maven Dependencies Not Downloading
	* Right click project -> Maven -> Update Project
	* Check Internet connection
	* Clear Maven cache: Delete .m2/repository folder
2. TestNG Not Found
	* Install TestNG Eclipse plugin
	* Add TestNG library to build path
3. Java Version Issues
	* Ensure JDK 17 is installed
	* Update project compliance level
	* Check build path JRE System Library
4. Browser Driver Issues
	* Update WebDriver version in pom.xml
	* Check browser version compatibility
	* Ensure browser is installed
	
## Notes
	* Always run Maven clean install after importing
	* Keep browser and WebDriver versions compatible
	* Check execution permissions on scripts
	* Update dependencies versions if needed

# Contact
	* Your Name - nguyenlongvux1@gmail.com
	* Project Link: https://github.com/yourusername/OpenCart_TestNG_Framework

--- THE END ---