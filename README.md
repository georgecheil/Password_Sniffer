# Password_Sniffer

### Readme for Scapy Sniffer

#### Overview:

This Python script utilizes the Scapy library to capture and analyze network packets on a specified interface (`eth0` in this case). The primary goal is to identify and extract login credentials (username and password) from packets containing HTTP data.

#### Prerequisites:

- Ensure that you have Python installed on your system.
- Install the required libraries using the following command:
  ```bash
  pip install scapy
  ```

#### Usage:

1. Open the terminal and navigate to the directory containing the script.
2. Run the script using the following command:
   ```bash
   python pass-sniffer.py
   ```
3. The script will start sniffing packets on the specified network interface (`eth0` by default).

#### Configuration:

- **Network Interface (`iface`):**
  - Adjust the `iface` variable in the script to match the network interface you want to monitor.

#### Functionality:

- The script defines two main functions:

  1. **get_login_pass(body):**
      - This function searches for potential login credentials in the HTTP body of packets.
      - It uses regular expressions to identify username and password fields in the payload.

  2. **pkt_parser(packet):**
      - This function is the packet parser.
      - It checks if the packet contains TCP, Raw, and IP layers, and if so, extracts the payload (HTTP body).
      - The extracted payload is then passed to `get_login_pass` to search for login credentials.
      - If credentials are found, the raw packet payload, username, and password are printed.

#### Customization:

- **User and Password Fields:**
  - The script includes lists of common field names for usernames (`userfields`) and passwords (`passfields`). Customize these lists to match the specific web application you are monitoring.

#### Exiting:

- To exit the script gracefully, press `Ctrl+C` in the terminal.
- The script will print "Exiting" and terminate.

#### Note:

- The script is designed for educational and informational purposes only.
- Ensure compliance with applicable laws and ethical considerations when using this script.
- Be aware that capturing and analyzing network traffic may raise privacy and security concerns. Use responsibly and only on networks you are authorized to monitor.

#### Disclaimer:

- The authors of this script are not responsible for any misuse or unintended consequences arising from its use.
- Use this script responsibly and respect privacy and legal considerations in your jurisdiction.
