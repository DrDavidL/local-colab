# Running Google Colab Notebooks Locally: A Guide for Medical Students

This guide will help medical students with no data science background learn how to download Google Colab notebooks and run them securely on their local computer using Visual Studio Code's built-in Jupyter notebook features.

## Table of Contents
1. [Why Run Notebooks Locally?](#why-run-notebooks-locally)
2. [Prerequisites](#prerequisites)
3. [Step 1: Install Required Software](#step-1-install-required-software)
4. [Step 2: Download the Notebook from Google Colab](#step-2-download-the-notebook-from-google-colab)
5. [Step 3: Set Up Your Project Folder](#step-3-set-up-your-project-folder)
6. [Step 4: Install Required Python Packages](#step-4-install-required-python-packages)
7. [Step 5: Open and Run the Notebook in VS Code](#step-5-open-and-run-the-notebook-in-vs-code)
8. [Step 6: Select or Create a Jupyter Kernel](#step-6-select-or-create-a-jupyter-kernel)
9. [Security Considerations](#security-considerations)
10. [Troubleshooting](#troubleshooting)
11. [Sample Notebook Information](#sample-notebook-information)

## Why Run Notebooks Locally?

Running notebooks locally offers several advantages:
- **Privacy**: Your data stays on your computer
- **Security**: No need to upload sensitive information to cloud services
- **Control**: Full control over your computing environment
- **Offline Access**: Work without internet connection
- **Performance**: Use your computer's full resources

## Prerequisites

- A computer running Windows, macOS, or Linux
- Administrator privileges to install software
- Basic familiarity with using your computer's file system
- Internet connection for initial setup

## Step 1: Install Required Software

### 1.1 Install Python

**For Windows:**
1. Go to [python.org](https://www.python.org/downloads/)
2. Download Python 3.9 or newer (recommended: Python 3.11)
3. Run the installer
4. **IMPORTANT**: Check "Add Python to PATH" during installation
5. Click "Install Now"

**For macOS:**
1. Go to [python.org](https://www.python.org/downloads/)
2. Download Python 3.9 or newer
3. Run the installer package
4. Follow the installation prompts

**For Linux (Ubuntu/Debian):**
```bash
sudo apt update
sudo apt install python3 python3-pip python3-venv
```

### 1.2 Install Visual Studio Code

1. Go to [code.visualstudio.com](https://code.visualstudio.com/)
2. Download VS Code for your operating system
3. Install following the default options

### 1.3 Install VS Code Extensions

1. Open Visual Studio Code
2. Click the Extensions icon in the left sidebar (or press `Ctrl+Shift+X`)
3. Search for and install these extensions:
   - **Python** (by Microsoft)
   - **Jupyter** (by Microsoft)

## Step 2: Download the Notebook from Google Colab

### Method 1: Direct Download from Colab
1. Open your notebook in Google Colab
2. Go to **File** → **Download** → **Download .ipynb**
3. Save the file to your Downloads folder

### Method 2: Download from Google Drive
1. If the notebook is shared via Google Drive link:
2. Click the link to open it in Colab
3. Go to **File** → **Save a copy in Drive** (if needed)
4. Then follow Method 1 to download

### Method 3: From GitHub (if available)
1. Navigate to the GitHub repository
2. Click on the `.ipynb` file
3. Click **Raw** button
4. Right-click and **Save As** to download

## Step 3: Set Up Your Project Folder

1. Create a new folder for your project:
   - **Windows**: Create folder in `Documents` (e.g., `Documents\medical-data-analysis`)
   - **macOS**: Create folder in `Documents` (e.g., `Documents/medical-data-analysis`)
   - **Linux**: Create folder in your home directory (e.g., `~/medical-data-analysis`)

2. Move your downloaded `.ipynb` file into this folder

## Step 4: Install Required Python Packages

Install the required packages using your system Python installation:

### 4.1 Open Terminal/Command Prompt

**Windows:**
- Press `Win + R`, type `cmd`, press Enter
- Or search for "Command Prompt" in Start menu

**macOS:**
- Press `Cmd + Space`, type "Terminal", press Enter

**Linux:**
- Press `Ctrl + Alt + T`

### 4.2 Install Required Packages

```bash
# Upgrade pip first
pip install --upgrade pip

# Install essential packages for data analysis
pip install pandas numpy matplotlib seaborn plotly

# Install Jupyter notebook support
pip install jupyter ipywidgets

# Install additional packages that might be needed
pip install scipy scikit-learn openpyxl xlrd

# For local LLM analysis (if using local_gpt_analysis.ipynb)
pip install pandasai-litellm litellm

# For Google Colab compatibility
pip install google-colab
```

**Note**: 
- These packages will be installed to your system Python
- The `google-colab` package helps with compatibility but some Colab-specific features may not work locally
- If you get permission errors, try adding `--user` flag: `pip install --user [package-name]`

## Step 5: Open and Run the Notebook in VS Code

### 5.1 Open VS Code in Your Project Folder

**Option 1 - From VS Code:**
1. Open VS Code
2. Go to **File** → **Open Folder**
3. Select your project folder

**Option 2 - From Terminal:**
```bash
# Navigate to your project folder first
cd path/to/your/medical-data-analysis
code .
```

### 5.2 Open the Notebook

1. In VS Code, click on your `.ipynb` file to open it
2. VS Code will automatically detect it's a Jupyter notebook and activate notebook mode

### 5.3 Run the Notebook

1. Click on the first code cell
2. Click the **Run** button (▶️) or press `Shift + Enter`
3. **VS Code will automatically prompt you to select a Jupyter kernel** - proceed to Step 6
4. Continue running cells one by one after kernel selection
5. Watch for any error messages and refer to troubleshooting section if needed

## Step 6: Select or Create a Jupyter Kernel

When you first try to run a cell, VS Code will prompt you to select a Jupyter kernel. This is where VS Code's built-in notebook features shine!

### 6.1 Automatic Kernel Selection (Most Common)

**If VS Code prompts you to select a kernel:**
1. Click **"Select Kernel"** when prompted
2. Choose **"Python Environments..."**
3. Select your system Python installation (usually shows as `Python 3.x.x` with a path)
4. VS Code will automatically create a Jupyter kernel for you

### 6.2 Manual Kernel Selection

**If you need to manually select a kernel:**
1. Look for the kernel selector in the top-right corner of the notebook (shows current kernel)
2. Click on it to open the kernel selection menu
3. Choose **"Select Another Kernel..."**
4. Select **"Python Environments..."**
5. Choose your Python installation

### 6.3 Creating a New Kernel (If Not Prompted)

**If VS Code doesn't automatically prompt you:**
1. Open the Command Palette (`Ctrl+Shift+P` or `Cmd+Shift+P`)
2. Type **"Jupyter: Select Interpreter to Start Jupyter Server"**
3. Select your Python installation
4. VS Code will create and connect to a Jupyter kernel

### 6.4 Kernel Selection Tips

**What to look for when selecting a Python environment:**
- Choose the Python installation where you installed the packages (Step 4)
- Usually shows as `Python 3.x.x` followed by the installation path
- Avoid any paths that mention `conda` unless you specifically use Anaconda
- If you see multiple options, choose the one that matches your system Python

**Kernel Status Indicators:**
- ✅ **Connected**: Kernel name appears in top-right corner
- ⚠️ **Not Connected**: Shows "No Kernel" or kernel selection prompt
- 🔄 **Starting**: Shows "Starting..." while kernel initializes

## Security Considerations

### Data Privacy
- **Never upload sensitive patient data** to cloud services
- Keep all data files in your local project folder
- Use anonymized or synthetic datasets for learning

### Code Safety
- **Review code before running** - understand what each cell does
- Be cautious with cells that:
  - Download files from the internet
  - Access system files
  - Install additional software
- When in doubt, ask a more experienced colleague

### VSCode Jupyter Benefits
- Automatic kernel management - no manual environment setup needed
- Built-in package management and installation
- Seamless integration with Python extensions
- Easy kernel switching between projects

## Troubleshooting

### Common Issues and Solutions

#### "Python not found" or "Command not recognized"
- **Solution**: Python wasn't added to PATH during installation
- **Fix**: Reinstall Python and check "Add Python to PATH"

#### "Module not found" errors
- **Solution**: Package not installed in your Python environment
- **Fix**: Install the missing package using `pip install [package-name]`
- **Alternative**: Use `pip install --user [package-name]` if you get permission errors

#### Notebook won't open in VS Code
- **Solution**: Jupyter extension not installed
- **Fix**: Install the Jupyter extension in VS Code

#### No kernel selection prompt appears
- **Solution**: VS Code may not detect Python properly
- **Fix**: 
  1. Open Command Palette (`Ctrl+Shift+P`)
  2. Type "Python: Select Interpreter"
  3. Choose your Python installation
  4. Try running a cell again

#### Kernel fails to start
- **Solution**: Python environment issues
- **Fix**: 
  1. Restart VS Code
  2. Ensure Python and Jupyter are properly installed
  3. Try selecting a different Python interpreter

#### Plots not displaying
- **Solution**: Interactive plots may not work the same as in Colab
- **Fix**: Try adding this code at the beginning of your notebook:
```python
import matplotlib.pyplot as plt
%matplotlib inline
```

#### Permission errors during package installation
- **Solution**: Insufficient permissions to install packages
- **Fix**: 
  - **Windows**: Run Command Prompt as Administrator
  - **macOS/Linux**: Use `sudo pip install [package-name]` or `pip install --user [package-name]`

#### Kernel keeps disconnecting
- **Solution**: System resource issues or conflicting packages
- **Fix**:
  1. Restart VS Code
  2. Clear any running Python processes
  3. Try creating a fresh kernel by reselecting the Python interpreter

### Getting Help

1. **VS Code Issues**: Check the VS Code documentation or Python extension docs
2. **Python Package Issues**: Search for the error message + package name
3. **General Python Help**: Python.org documentation and tutorials
4. **Medical Data Analysis**: Consult with colleagues familiar with data analysis

## Sample Notebook Information

This repository includes two notebooks designed for progressive learning:

### 📊 Start Here: `local_Part_2_Exploring_Data.ipynb`

**Begin with this notebook** to learn traditional data analysis methods:
- Data loading and cleaning techniques
- Statistical summaries and descriptive analysis
- Data visualization (histograms, box plots, scatter plots)
- Interactive widgets for data exploration
- Correlation analysis and pattern recognition
- Traditional Python-based data science workflows

**Key Libraries Used:**
- `pandas`: Data manipulation and analysis
- `numpy`: Numerical computing
- `matplotlib`: Basic plotting
- `seaborn`: Statistical data visualization
- `plotly`: Interactive visualizations
- `ipywidgets`: Interactive notebook widgets

### 🤖 Advanced: `local_gpt_analysis.ipynb`

**After mastering the basics**, explore this notebook to learn:
- Natural language data analysis using local large language models
- Secure AI-powered data exploration that runs entirely on your computer
- How to ask questions about your data in plain English
- Local LLM setup with Ollama and qwen3:8b model
- Privacy-preserving AI analysis for medical data

**Additional Requirements:**
- Ollama installed locally
- qwen3:8b model downloaded
- Additional packages: `pandasai-litellm`, `litellm`

### 📋 Dataset Information

Both notebooks use the same dataset:
- Deidentified diabetes dataset from University of Virginia
- 390 patients with various health metrics
- Safe for educational use
- Perfect for learning medical data analysis techniques

### 🎯 Recommended Learning Path

1. **Start with `local_Part_2_Exploring_Data.ipynb`**
   - Learn fundamental data science concepts
   - Master traditional analysis techniques
   - Understand data visualization principles
   - Build confidence with Python and pandas

2. **Progress to `local_gpt_analysis.ipynb`**
   - Explore cutting-edge local AI analysis
   - Learn natural language data querying
   - Understand privacy-preserving AI workflows
   - Experience the future of secure medical data analysis

## Next Steps

Once you're comfortable running notebooks locally:

1. **Learn Python Basics**: Understanding basic Python will help you modify and create your own analyses
2. **Explore Data Science**: Consider online courses in medical data analysis
3. **Practice with Your Own Data**: Start with anonymized datasets relevant to your field
4. **Join Communities**: Look for medical informatics or healthcare data science groups

## Additional Resources

- [Python for Everybody](https://www.py4e.com/) - Free Python course
- [Pandas Documentation](https://pandas.pydata.org/docs/) - Data analysis library
- [Matplotlib Tutorials](https://matplotlib.org/stable/tutorials/index.html) - Plotting library
- [VS Code Python Tutorial](https://code.visualstudio.com/docs/python/python-tutorial) - Official guide

---

**Remember**: This setup process only needs to be done once. After initial setup, you can simply:
1. Open VS Code in your project folder
2. Open your notebook file
3. VS Code will automatically connect to your Jupyter kernel
4. Start working with notebooks immediately

**Stay Safe**: Always prioritize patient privacy and data security in your work.
