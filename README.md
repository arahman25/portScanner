# portScanner
# Simple port scanner for pentesting
# to communicate using TCP/UDP with other machines
import socket 

# to print some statements in different colors
import termcolor

# to inititate Scan Request function
def scan(targets,ports):
  for port in range (1,ports):
    scan_port(targets,port)

# to inititate Port Scan function
def scan_port(ipaddress,port):
  try:  
    sock = socket.socket()
    sock.connect((ipaddress, port))
    print("[+] Port Opened " + str(port))
    sock.close()
  except:
    print("[-] Port Closed " + str(port))

targets = input("[*] Enter Targets To Scan (split by comma: ")
ports = int(input("[*] Enter How Manay Ports You Want to Scan: "))
if ',' in targets:
  print("[*] Scanning Multiple Targets")
  for ip_addr in targets.split(',')
    scan(ip_addr.strip(' '),ports)
  else:
    scan(targets,ports)
