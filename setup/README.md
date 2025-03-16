<h1>
  <span class="headline">ML Workflow and Best Practices</span>
  <span class="subhead">Setup</span>
</h1>

## Setup

Before starting the lessons, you'll need to set up your Python environment with the necessary packages. Follow these steps in your terminal:

1. **Ensure Python is Installed**

   ```sh
   python --version  # Should be Python 3.8 or higher
   ```

   If Python is not installed, download it from [python.org](https://python.org)

2. **Create and Activate a Virtual Environment**

   ```sh

   python -m venv env
   source env/bin/activate

   ```

3. **Install Required Packages**

   ```sh
   pip install jupyter numpy pandas scikit-learn matplotlib seaborn
   ```

4. **Verify Installation**
   ```sh
   python -c "import numpy; import pandas; import sklearn; import matplotlib; import seaborn; print('All packages installed successfully!')"
   ```

## Jupyter Notebook Setup

1. **Create a Directory**
   - On your machine, create a directory or folder named `ml-workflow-and-best-practices` where you can save all the data and the jupyter notebooks concerned with this module.
2. **Open Command Prompt**

   - If using **Command Prompt**, type:
     ```sh
     jupyter notebook
     ```
     This will open Jupyter Notebook in your default web browser.

3. **Navigate to the Module Directory**

   - In the Jupyter Notebook interface, browse to the folder created in step 1. This is where you want to create your notebook.

4. **Create a New Jupyter Notebook**
   - Click **New** (top-right corner) → **Python 3** to create a new notebook.
   - Rename the notebook by clicking on the **default name ("Untitled")** and entering the name as:
     ```
     <ML-WORKFLOW-AND-BEST-PRACTICES>.ipynb
     ```
5. **Write and Execute Python Code**

   - You can copy the demo python code given in the lessons or tryout your own code too.
   - Click inside a code cell and paste the demo code or type your Python code.
   - Press **Shift + Enter** to run the code in the cell.

6. **Save and Close the Notebook**

   - Click **File → Save and Checkpoint** to save progress.
   - To close, select **File → Close and Halt**, then close the browser tab.

7. **Shut Down Jupyter Notebook**
   - In the terminal where Jupyter Notebook is running, press **Ctrl + C** and type `Y` when prompted.
