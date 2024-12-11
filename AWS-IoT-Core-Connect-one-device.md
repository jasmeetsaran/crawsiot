# AWS IoT Core - Connect one device


AWS IoT (Core) > Connect > Connect one device

1. Thing properties
	- Thing name - _required_
		- Thing type _- optional_
		- Searchable thing attributes _- optional_
		- Thing groups _- optional_
		- Billing group _- optional_
2. Choose platform and SDK
3. Download connection kit (connect_device_package.zip) on Laptop/Computer
4. Transfer it using Secure copy protocol (SCP) to Raspberry Pi
```
scp "C:\Users\<pc-username>\Downloads\connect_device_package.zip" <pi-username>@<pi-IP-Hostname>:/home/<pi-username>
```
5. Unzip connection kit on your device
```
unzip connect_device_package.zip -d connect_device_package
```
6. Edit and remove python check section on top of the (start.sh) file
```
nano connect_device_package/start.sh
```
7. Prepare python virtual environment
```
python3 -m venv ~/aws_iot
source ~/aws_iot/bin/activate
python3 -m pip install --upgrade pip setuptools wheel
```
8. Add execution permissions
```
chmod +x start.sh
```
9. Run connection kit
```
./start.sh
```



