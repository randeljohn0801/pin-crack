This project is a Python-based brute-force tool designed to guess a PIN code for an HTTP application running on a specific port. It automates multiple PIN attempts and checks for a successful response from the server. The main challenge is identifying the correct server address, port, and required request parameters.

How to Run
Starting the Server
Launch the provided executable (.exe) file to start the server.

Open a web browser and navigate to http://127.0.0.1:8888.

The application will be ready to accept PIN inputs.

Running the Python Script
Open the project folder in Visual Studio Code or any Python IDE.

Ensure Python is installed on your machine.

Install the required dependencies (such as requests) if they are not already installed.

Run the script using the terminal:

bash
Copy
Edit
python brute_force.py
The script will attempt all 3-digit PIN combinations and display its progress in the console.

Approach
Finding the Address and Port
Wireshark was used to capture network traffic when running the executable. By analyzing the packets, it was determined that the server listens on 127.0.0.1 (localhost) and port 8888.

Identifying Required Parameters
By following the HTTP stream in Wireshark, it was observed that the server expects the PIN to be submitted under the magicNumber field. The script was crafted accordingly to send the PIN using this field name.

Handling Performance Constraints
There were no major technical issues; however, the script is somewhat slow in finding the correct PIN due to the nature of brute-force attacks.

Lessons Learned
Gained a deeper understanding of how web servers defend against brute-force attacks.

Learned how basic brute-force techniques operate in practice.

Recommendations for Security Improvements
Increase complexity by allowing PINs to include letters, symbols, or longer combinations.

Implement rate-limiting or lockout mechanisms to deter brute-force attempts.

