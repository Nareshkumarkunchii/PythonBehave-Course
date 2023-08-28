# PythonBehave - Overview
Python selenium automation using Behave BDD Framework 


# Behave : 
Behave is a Python BDD (Behavior Driven Development) framework which makes it easy to write tests in a natural language style.behave uses tests written in a natural language style, backed up by Python code.

It has features(.feature) files and steps(.py) files.
➜ Feature file : A feature file is a natural language format describing a feature of an application or scenario of expected outcomes.
➜ Steps file : Steps file is a normal python file where execution code as written in it based on steps in the feature file.

# Contents 
  1. Introduction Behave,BDD 
  2. Installation on Mac
      ➜ Create Virtual Environment in mac
      ➜ Install Python and Pycharm IDE on Mac
      ➜ Install Selenium 
      ➜ Install Ghirkin plugin on pycharm
      ➜ Install Behave
  3. Folder Stucture
  4. Gherkin language - Gherkin Keywords
  5. About Feature File
  6. About Step definition File
  7. Writing First Test and running feature files
  8. Passing Parameters to Steps
  9. Scenario 
  10. Scenario outline
  11. Adding Multiple scenarios with multiple parameters
  12. Background
  13. context -variable offenly to share data between steps
  14. Tags in Behave
  15. Allure Reports - Generate Reports in Behave
  16. How to Generate Custom Report
  17. Hooks / Fixtures - Environment.py - tear down functions in Behave
  18. End - thank you
      
# 1. Introduction to Behave,BDD
  ➜ Behave is BDD framework, is a Cucumber variant for Python.. BDD is an agile software development technique 
  that encourages collaboration between developers, QA and non-technical teams in software project.
  ➜ As per BDD, the implementation of functionality comes at a later stage as tests should be created first.
  ➜ Behave uses tests written in a natural language style, backed up by Python code.

# 2. Installation on Mac
  
   ➜ Create Virtual Environment in mac :
  
    Step 1 : enter in cmd :➜  which python3
    step2 : type : which python3 and copy path :➜ /Library/Frameworks/Python.framework/Versions/3.11/bin/python3
    step 3 : create environment with name on above default path by cmd :
    ➜ virtualenv --python=/Library/Frameworks/Python.framework/Versions/3.11/bin/python3 venv_name
    step 4 : activate venv by cmd :
    example as ➜  source venv_medigo_bdd_cases/bin/activate  ➜ successfully created venv and activated.

   ➜ Install Python and Pycharm IDE on Mac   
   
      ➜ Follow below steps to install Python and Pycharm IDE  using following steps
  
      1. Using python installer :
      ---------------------------
      Step 1 : download latest version of installer package from link: https://www.python.org/downloads/ on your Mac
      Step 2 : Once the installer is downloaded, open it and follow the on-screen instructions to install Python.
    
      2. Using Home brew : 
      --------------------
      ➜ if brew not seen in mac install brew
        /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
      ➜ run in terminal : 
        brew install python3 
        
      3. Install PyCharm :
      -------------------
      Step 1: Go to the PyCharm website and Download :
          https://www.jetbrains.com/pycharm/ -  download the community edition (free)
      Step 2: install PyCharm :
          Once the downloaded open ".dmg" file and drag the PyCharm icon into the Applications folder.
      Step 3: Launch PyCharm :     
          Navigate to your Applications folder and open PyCharm
          
      4. Add Virtual Env to PyCharm on Mac :
      -------------------------------------
      activate venv by cmd : source venv_medigo_bdd_cases/bin/activate  ➜ activated venv
      Now add this Venv to pycharm
      
      step 1 : activate Venv created from above steps
      step 2 : which python3 cmd and copy path : /Users/gradientm/venv_name/bin/python3
      step 3 : ➜ go to new project on pycharm and add click settings
               ➜ search interpretor and select inexisting interpreter option on pycharm
               ➜ add path "/Users/gradientm/venv_name/bin/python3 " and Apply and Venv updated.
      
  ➜ Install Selenium and Behave BDD :
  
     Enter following commands on terminal
       ➜ pip install selenium
       ➜ pip install behave 
    Make sure you also have the Chrome/Firefox divers downloaded and added to your system path.  
  ➜ Install Ghirkin plugin on pycharm

      Click on Pycharm setting and go to Plugins tab and search "ghirkin"  
      ➜ Ghirkin plug-in and install and apply.

# 3. Folder Stucture 

  Behave works with three types of files:
    1. feature files written by your Business Analyst / Sponsor / whoever with your behaviour   scenarios in it.
    2. “steps” directory with Python step implementations for the scenarios.
    3. optionally some environmental controls (code to run before and after steps, scenarios, features or the whole shooting match).
      
    Behave Folder Structure:
    --------------------
    ➜Project /project directory 
	  +-- features
			    +-- steps
							step1.py
							step2.py
              ....
			  feature1.feature
				feature2.feature
        .....
			  environment.py
		+--➜ reports
    External libraries

     // or simply
    +--features/
    |   +--steps/       # -- Steps directory
    |   |    +-- *.py   # -- Step implementation or use step-library python files.
    |   +-- *.feature   # -- Feature files.    


# 4. Gherkin language - Gherkin Keywords

  Behave features are written using a language called "Gherkin" (with some modifications).
  Gherkin language is basically the normal English language with some basic rules. It has introduced a few keywords with which the tests     should be written. And these Gherkin language tests are mapped with code . 
  
  Keywords of the Gherkin language:
      
      Feature
      Background
      Scenario
      Scenario outline
      Given
      When
      Then
      And
            
  Feature keyword — Provides a high level description of the software feature.
  Scenario keyword — indicates the title of the test case.
  Given keyword — describes a set of pre-conditions for the Selenium test automation scenario
  When keyword — Describes the scenario steps 
  Then keyword — Describes the Scenario outcome 
  And — Used to provide additional steps. It is used along with other keywords such as Given, When, and Then 

  Example of a BDD test written using Gherkin language : Login functionality
    
    Feature: Login to web application
    
        Scenario: Login with valid username and password
          Given user on chrome web login page 
          Then user enter"username" and "password"
          And user click on login button
          Then user successfully logged into application     

# 5. About Feature File

  Features are composed of scenarios. They may optionally have a description, a background and a set of tags. 
  Feature files in Gherkin are plain simple text files that have a .
  feature extension and can be pivotal in business driven development.A feature file can contain one or more scenarios.
  Relevant Tags (@ Tag) are used to differentiate between different Scenarios. 
  In its simplest form a feature looks like:
        
    Feature: feature name
      Scenario: some scenario
      Given some condition
       Then some result is expected.
    

# 6. About Step definition File
  Step functions are the implementation of the feature file steps. 
  They are implemented in Python modules present in your "steps" directory. 
  All the Python files (.py) are loaded before executing your features because .py files are used to search the step implementations.

    Step implementation example :

    from behave import given, when, then
    
    @given("user on chrome web login page")
    def methodOne(context):
    print("chrome web login page")
    
    @when(' user enter"username" and "password" ')
    def methodTwo(context):
    print("enter username and pswrd ")
    
    @when("user click on login button")
    def methodThree(context):
    print("login button")
    
    @then("user successfully logged into application")
    def methodFive(context):
    print(" successfully logged in ")
  
  # 7. Writing First Test and running feature files

  
         
    
    
















  
