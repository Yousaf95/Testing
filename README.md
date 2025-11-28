# Example: Using Our yProv4SQA with the iTwinAI Repository

In this example, we demonstrate how to use our library by analyzing the the [iTwinAI GitHub repository](https://github.com/interTwin-eu/itwinai).  

This repository already utilizes SQAaaS and contains existing assessments. We will use it to  Showcase the capabilities of our library and Extract insights related to software quality and provenance.

## **Clone the repository and navigate to the directory:**
   ```bash
   git clone https://github.com/username/yProv4SQA.git
   cd yProv4SQA
   ```

## **Setup the environment and install dependencies:**

### 1. Create and activate a virtual environment (recommended)

   ```bash
   # Create a virtual environment
   python -m venv yProv4SQA_venv

   # Activate the virtual environment (Linux/macOS)
   source yProv4SQA_venv/bin/activate

   # Activate the virtual environment (Windows)
   yProv4SQA_venv\Scripts\activate
   ```
### **2. Install the library and required dependencies:**
   ```bash
   pip install -e .
   pip install requests
   ```
This installs the library in editable mode, allowing you to modify the code and test changes immediately. It also installs the requests library, which is required to run the examples.

## **SFetch SQA reports:**
   ```bash
   fetch-sqa-reports itwinai
   ```
This command fetches all SQAaaS assessments for the `itwinai` repository from the EOSC-Synergy GitHub space.
[EOSC-Synergy GitHub space](https://github.com/EOSC-synergy)

The library will:
- Download all available reports  
- Remove duplicates and older versions  
- Clean and preprocess the data  
- Produce a final assessment folder for generating the provenance document


**Generate provenance documents:**
   ```bash
   process-provenance ./itwinai_SQAaaS_reports
   ```

**Compare two assessments:**
   ```bash
   compare ./provenance.json 59 87
   ```

This will give you a structured view of how the software quality has changed between the first and second assessments.
