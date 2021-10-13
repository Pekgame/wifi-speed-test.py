This is python project that can test your Wi-Fi!

use this code!
and don't forgot to type this in cmd
pip install speedtest

import os
try:
  import speedtest
except:
  os.system('pip install speedtest')
  import speedtest

os.system('cls')
test = speedtest.Speedtest()

print("Loading server list...")
test.get_servers() # -> get list of servers
print("Choosing best server...")
best = test.get_best_server() # -> choose best server
print(f"Found: {best['host']} located in {best['country']}")

print("Performing download test...")
download_result = test.download()
print("Performing upload test...")
upload_result = test.upload()
ping_result = test.results.ping

print(f"Download speed: {download_result / 1024 / 1024:.2f} Mbit/s")
print(f"Upload speed: {upload_result / 1024 / 1024:.2f} Mbit/s")
print(f"Ping: {ping_result:.2f} ms")
