# Wireless Alerting System
## Abstract
This project presents the development and implementation of a wireless dashboard for real-time machine error monitoring using the Arduino IoT Cloud. The system aims to enhance operational efficiency and streamline error resolution across multiple departments within an industrial setting. Utilizing ESP32 microcontrollers, the dashboard collects and transmits machine error data wirelessly, providing instant updates accessible via mobile devices and desktops. The project features a custom-designed PCB and a 3D-printed case to house the electronics. Key functionalities include department-wide error dashboards, efficiency tracking using Google Sheets, and mobile accessibility for on-the-go monitoring. This innovative solution facilitates proactive maintenance, minimizes downtime, and improves overall productivity.

## Repository Structure
### Codes
This section contains the code necessary for the operation of the Wireless Alerting System. The repository is organized into two main subdirectories: Arduino IoT Cloud Sketch and Google Sheets App Script.

- **Arduino_IoT_Cloud**
In this subdirectory, you will find the code to be uploaded to the ESP32 microcontroller using the Arduino IoT Cloud platform. The code handles the collection of machine error data and its transmission to the cloud.
- **Google_Sheets_App_Script**
This subdirectory contains the Google Sheets App Script code, which is used to track efficiency and log machine errors in a Google Sheet.

- **3D Models**: STL files for 3D printing the custom-designed case for the electronics.
- **PCB Design Files**: Schematic and layout files for the custom PCB design, including BOM (Bill of Materials) and Gerber files for manufacturing.

# Setting Up Arduino IoT Cloud

## 1. Adding Devices and Programming with Arduino IoT Cloud

1. **Create an Account and Setup**
   - Sign up for an Arduino IoT Cloud account if you haven't already.

2. **Create a New Thing**
   - Log into Arduino IoT Cloud.
   - Click on "Things" and then "Create a New Thing".
   - Name your device (e.g., ESP32), select the board (ESP32), and choose a connectivity type (Wi-Fi).

3. **Setting Up Variables**
   - Define variables for your project (e.g., error codes, timestamps).
   - Specify data types and any default values.

4. **Create Dashboards**
   - Design dashboards to visualize your variables in real-time.
   - Arrange widgets to display machine error data effectively.

5. **Programming the ESP32**
   - Write your Arduino sketch (`machine_error_monitor.ino`) to read sensor data (e.g., machine error data) and update variables.
   - Use the Arduino IDE or Arduino IoT Cloud's online editor to upload your sketch to the ESP32.

6. **Testing**
   - Ensure your ESP32 is connected to Wi-Fi and transmitting data correctly.
   - Monitor the Arduino IoT Cloud dashboard to verify data reception.

# Integrating with Google Sheets App Script

## 2. Writing and Deploying Google Sheets App Scripts

1. **Create a Google Sheet**
   - Open Google Sheets and create a new spreadsheet.
   - Set up columns for error logs, timestamps, and any other relevant data.

2. **Enable Google Apps Script**
   - In Google Sheets, go to "Extensions" > "Apps Script" to open the script editor.

3. **Write the Error Logger Script**
   - Write a script (`ErrorLogger.gs`) to receive data from Arduino IoT Cloud.
   - Use functions like `doPost(e)` to handle incoming data via HTTP requests.
   - Parse incoming data and append it to your Google Sheets.

4. **Dashboard Updater Script**
   - Create another script (`DashboardUpdater.gs`) to update department-wide dashboards with the latest error data and efficiency metrics.

5. **Deploy the Scripts**
   - Save and deploy your scripts as a web app.
   - Set permissions to run the script as you (the owner) or anyone accessing the web app.
   - Obtain the deployment URL for later use in your Arduino IoT Cloud setup.

# Integration and Testing

1. **Connect Arduino IoT Cloud to Google Sheets**
   - Use the deployment URL of your Google Apps Script in Arduino IoT Cloud.
   - Configure the HTTP integration to send data from Arduino IoT Cloud to your Google Sheets App Script endpoint.

2. **Monitor and Debug**
   - Test the entire system to ensure data flows from ESP32 → Arduino IoT Cloud → Google Sheets correctly.
   - Use debugging tools in Arduino IoT Cloud and Google Sheets to troubleshoot any issues.

By following these steps, you can successfully integrate your Arduino IoT Cloud setup with Google Sheets, allowing for real-time logging and dashboarding of machine error data.
