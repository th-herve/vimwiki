# Python virtual environment

Allow to have multiple version of a library or python itself.

Its good practice to have one for each project.

Help build the requirement file.



# Create an environment

1. Cd project_folder
1. `virtualenv envName`

# Activate and use environment

1. In terminal, in the folder of the project: windows: `venv\Scripts\activate` Linux: `source envName/bin/activate`
2. Now there is the name of the environment in bracket in the terminal
3. Install the packages you need and do your project
4. Add the requirement in a txt file with: `pip install -r requirements.txt`
4. Deactivate with: deactivate 

>note: using wsl, if step 1 fail, try using the full path to the env: source /mnt/c/Users/YourUsername/Projects/YourFlaskProject/venv/bin/activate

# How to install

windows:

1. `pip install virtualenv`

Linux:

1. sudo apt install python3-virtualenv
2. pip install virtualenv

