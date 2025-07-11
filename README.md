This project provides a Python code to track the approximate geographical location and service provider of a phone number and visualize it on an interactive map. It leverages the `phonenumbers` library for parsing and basic information, the `opencage` library for precise geocoding, and `folium` for map generation.

## ✨ Features

* **Phone Number Parsing:** Utilizes the `phonenumbers` library to parse and validate phone numbers, extracting country and national numbers.

* **Location Lookup:** Determines the approximate geographical location (country/region) associated with the phone number.

* **Service Provider Identification:** Identifies the telecommunication service provider for the given number.

* **Geocoding:** Converts the textual location into precise latitude and longitude coordinates using the OpenCage Geocoding API.

* **Interactive Map Generation:** Creates an interactive HTML map (`myLocation.html`) with a marker placed at the determined coordinates, showing the location details on hover.

## 🛠️ Prerequisites

Before running the script, ensure you have Python 3.x installed on your system. You will also need the following Python libraries:

* `phonenumbers`

* `folium`

* `opencage`

## 🚀 Installation

You can install the required libraries using `pip`. You can run this command directly in your R Markdown document if you have `reticulate` configured to use a Python environment.

```{python, eval=FALSE}
# Install Python packages if not already installed
# You might need to set up a Python environment for reticulate first
# For example: reticulate::py_install(packages = c("phonenumbers", "folium", "opencage"))
import subprocess
import sys

def install_package(package):
    try:
        __import__(package)
        print(f"{package} is already installed.")
    except ImportError:
        print(f"Installing {package}...")
        subprocess.check_call([sys.executable, "-m", "pip", "install", package])
        print(f"{package} installed successfully.")

install_package("phonenumbers")
install_package("folium")
install_package("opencage")
```

## 🔑 API Key Setup

This project uses the OpenCage Geocoding API to convert location names into geographical coordinates. You will need to obtain a free API key:

1.  Go to the [OpenCage Geocoding website](https://opencagedata.com/).

2.  Sign up for a free account to get your API key.

Once you have your API key, replace `'YOUR API'` in the provided script with your actual key:

```python
Key='YOUR API' # Replace 'YOUR API' with your actual OpenCage Geocoding API Key
```

## 📝 Usage

Follow these steps to run the script:

1.  **Create `number.py`:**
    In the same directory as your main script (e.g., `tracker.py`), create a new Python file named `number.py`. This file will store the phone number you want to track.

    ```python
    # number.py
    num = "+12025550100" # Replace with the target phone number, including the country code (e.g., +1 for USA, +44 for UK).
    ```

2.  **Save the main script:**
    Save the provided Python code (your `tracker.py` or similar) in the same directory. Ensure you have replaced `'YOUR API'` with your actual OpenCage Geocoding API key.

3.  **Run the script:**
    Open your terminal or command prompt, navigate to the directory where you saved the files, and run the script:

    ```bash
    python your_script_name.py
    ```

    (Replace `your_script_name.py` with the actual name of your main Python script file.)

    Alternatively, if you have `reticulate` set up in R, you could potentially run the Python script directly from an R chunk, though for a full script, running from the terminal is often more straightforward.

    ```{python, eval=FALSE}
    # Example of how you might run the script if it were in a single file
    # Note: This assumes your Python environment is correctly configured with reticulate
    # and that the 'number.py' and 'tracker.py' files are accessible.
    # import subprocess
    # subprocess.run(["python", "your_script_name.py"])
    ```

## 🖥️ Output

Upon successful execution, the script will:

* Print the detected location and service provider to your console.

* Generate an HTML file named `myLocation.html` in the same directory. Open this file in any web browser to view the interactive map with the phone number's approximate location marked.

## ⚠️ Disclaimer

* **Educational Use Only:** This tool is intended for educational purposes and personal experimentation.

* **Accuracy:** The accuracy of the location and service provider information is dependent on the data provided by the `phonenumbers` library and the OpenCage Geocoding API. It may not always be precise or real-time.

* **Privacy & Legal Compliance:** Always ensure you have the legal right and explicit consent to track any phone number. Do not use this tool for illegal, unethical, or malicious activities. Respect privacy laws and regulations in your jurisdiction.
