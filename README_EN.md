# HTTP Request Batch Tool GUI V1 - User Guide

[HTTP请求批量工具 GUI V1 中文说明书](https://github.com/allen-x233/HttpRequestTool_GUI/blob/main/README_ZH.md)

## Introduction
This tool provides a visual GUI for batch reading HTTP request data from Excel files, automatically sending requests, and writing responses back to Excel. It supports proxy, certificate import, timeout settings, request interval, forced HTTPS, SSL verification, and more. It is ideal for API testing and automated batch requests.

---
![image](https://github.com/user-attachments/assets/0713f8cf-ef2c-41d3-9fbd-b8d727b0fee4)
![image](https://github.com/user-attachments/assets/746fa021-959a-4c2b-b450-a43f9597b715)
![image](https://github.com/user-attachments/assets/a5045f61-61aa-4902-b87a-97ca375bcef7)
![image](https://github.com/user-attachments/assets/771a282b-051f-44bf-8031-39116d6eea17)


## Features Overview
- **Batch HTTP Requests from Excel**: Automatically send HTTP requests defined in Excel.
- **Request Interval**: Customize the wait time between requests to avoid server rate limits.
- **Timeout Setting**: Set a timeout for each request to prevent hanging.
- **Proxy Support**: Supports HTTP/HTTPS proxies for debugging or packet capture.
- **SSL Verification Modes**: Choose to disable SSL verification or import a custom CA certificate.
- **Force HTTPS**: Automatically upgrade all requests to HTTPS.
- **Output History**: Automatically records each output file for easy tracking.
- **Detailed Logs**: Real-time logs for every step and error, making troubleshooting easy.

---

## GUI Elements Explained

### 1. Input File Selection
- **Function**: Select the Excel file to process (must include columns: Request, Response Headers, Response Body, Full Response, Remarks).
- **How to Use**: Click "Browse" to select your Excel file.

### 2. Output Directory
- **Function**: Set the directory to save the result Excel file.
- **How to Use**: Click "Browse" to select a folder or enter the path manually.

### 3. Request Interval (seconds)
- **Function**: Set the wait time between each request (in seconds).
- **Tip**: Set to 1 second or more if the target server has rate limits.

### 4. Timeout (seconds)
- **Function**: Set the timeout for each HTTP request (in seconds).
- **Tip**: Usually set between 5 and 30 seconds.

### 5. Force HTTPS
- **Function**: When checked, all requests are automatically upgraded to HTTPS.
- **When to Use**: Use when the API only supports HTTPS.

### 6. Proxy Settings
- **Function**: Supports HTTP/HTTPS proxy for debugging or packet capture.
- **How to Use**:
  - Check "Use Proxy"
  - Enter proxy IP and port (e.g., 127.0.0.1:8080)

### 7. SSL Verification Mode
- **Option 1: Disable SSL Verification**
  - For debugging with self-signed certificates.
  - Not secure for production.
- **Option 2: Import CA Certificate**
  - Select a PEM-format CA certificate (e.g., exported from a packet capture tool).
  - The tool will use this certificate for SSL verification.
  - Note: DER format (.der) is not supported. Convert to .pem if needed.

### 8. Output History
- **Function**: Shows recently generated result files. Click to open quickly.

### 9. Log Output
- **Function**: Real-time display of progress, detailed logs, and errors.
- **Purpose**: Helps troubleshoot failed requests.

### 10. Start Button
- **Function**: Click to start batch processing.

---

## How to Use

1. Prepare an Excel file in the required format (see below).
2. Launch the program and select the input file and output directory.
3. Set request interval, timeout, proxy, SSL, and other parameters as needed.
4. Click "Start Processing" and wait for the progress bar to complete.
5. After completion, check the output history for the result file.

---

## Excel File Format

- **Request**: The original HTTP request (e.g., GET/POST, including URL, headers, body).
- **Response Headers**: Filled automatically by the program.
- **Response Body**: Filled automatically by the program.
- **Full Response**: Filled automatically (includes status line, headers, body).
- **Remarks**: Optional notes.

---

## Certificate Import Instructions

- Only PEM format certificates are supported (text format, starts with -----BEGIN CERTIFICATE-----).
- If you have a DER (.der) file, convert it with:
  ```
  openssl x509 -inform der -in cacert.der -out cacert.pem
  ```
- Select the converted .pem file for import.

---

## FAQ

- **Certificate Import Error**: Make sure it's a valid PEM file and the content is complete.
- **Proxy Connection Fails**: Check if the proxy IP/port is correct and the proxy software is running.
- **Request Timeout**: Increase the timeout or check the network/server status.
- **Cannot Write Output File**: Make sure you have write permission or close any open Excel files.

---

## Notes

- This tool is for legal use only, such as API testing and automation.
- Be aware of data security risks when using proxies or disabling SSL verification.
- Always back up your original Excel files before processing.

---

For questions or suggestions, please contact the [developer](https://github.com/allen-x233/HttpRequestTool_GUI). 
