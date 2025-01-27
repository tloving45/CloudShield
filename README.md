# CloudShield
Security JSON Scanner

## Overview

CloudShield is a web application that helps users identify and mitigate potential security vulnerabilities in their cloud infrastructure. Users can upload a JSON configuration file describing their cloud resources and security settings. The application analyzes the configuration and provides a report highlighting security issues and recommendations for improvement.

## Features

- File Upload: Users can upload JSON configuration files.
- Configuration Analysis: The application parses and analyzes the JSON file for common security issues.
- Report Generation: Generates a security report with identified issues and recommendations.

## Prerequisites

- Python 3.7+
- pip (Python package manager)
- Git (for cloning the repository)

## Installation

1. Clone the repository:
git clone https://github.com/tloving45/cloud-security-analyzer.git
cd cloudshield

2. Create a virtual environment (optional but recommended):
python -m venv venv
source venv/bin/activate # On Windows, use venv\Scripts\activate

3. Install the required packages:
pip install -r requirements.txt


## Configuration

1. Create an `uploads` directory in the project root:
mkdir uploads

2. (Optional) Adjust the maximum file size in `app.py`:
app.config['MAX_CONTENT_LENGTH'] = 16 * 1024 * 1024 # 16MB max file size


## Running the Application

1. Start the Flask application:
python app.py

2. The application will start running on `http://localhost:5000`

## Usage

### Uploading a Configuration File

1. Use a tool like cURL or Postman to send a POST request to `http://localhost:5000/upload`
2. Set the request body to `form-data`
3. Add a key named `file` with the value being your JSON configuration file

Example cURL command:
curl -X POST -F "file=@/path/to/your/config.json" http://localhost:5000/upload

### Interpreting the Results

The application will return a JSON response with:
- A summary of identified security issues
- Detailed descriptions of each issue
- Recommendations for mitigating each issue

## Screenshots

### File Upload Interface
![File Upload Interface](https://example.com/file_upload_interface.png)

### Analysis Results
![Analysis Results](https://example.com/analysis_results.png)

## Security Considerations

- This application is a prototype and should not be used in production without further security enhancements.
- Implement user authentication and authorization before deploying.
- Ensure proper input validation and sanitization for all user inputs.
- Regularly update dependencies to patch any security vulnerabilities.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
