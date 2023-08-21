# PythonBehave - Overview
Python selenium automation using Behave BDD Framework 


# Behave : 
Behave is a Python BDD (Behavior Driven Development) framework which makes it easy to write tests in a natural language style.behave uses tests written in a natural language style, backed up by Python code.

# Contents 
  1. Introduction Behave,BDD 
  2. Installation on Mac
      ➜ Create Virtual Environment in mac
      ➜ Install Python and Pycharm IDE on Mac
      ➜ Install Selenium 
      ➜ Install Ghirkin plugin on pycharm
      ➜ Install Behave
  3. Folder Stucture
  4. About Feature File
  5. Gherkin language - Gherkin Keywords
  6. About Step definition File
  7. Hooks / Fixtures - Environment.py - tear down functions in Behave
  8. Writing First Test and running feature files
  9. Passing Parameters to Steps
  10. Scenario 
  11. Scenario outline
  12. Adding Multiple scenarios with multiple parameters
  13. Background
  14. context -variable offenly to share data between steps
  15. Tags in Behave
  16. Allure Reports - Generate Reports in Behave
  17. How to Generate Custom Report 
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
      
    
      
